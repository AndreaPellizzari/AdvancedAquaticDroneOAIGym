$$\underline{\textbf{Appunti codice progetto: }\textit{Davide Fozzato} - \textit{Andrea Pellizzari}}$$

# Spiegazione funzioni ausiliarie

## get_cost(node_state, grid, cost_dict)

Funzione che serve per calcolare il costo di movimento per entrare in uno stato. Dato il dizionario di costi (cost_dict) prende il tipo di cella nella griglia e restituisce il costo associato, altrimenti associa il costo standard 1 (che rappresenta il caso della pompa di energia). Questo determina il contributo al costo reale $g$ nel calcolo della funzione $f$.

## present_with_higher_cost(queue, node)

Funzione che serve per controllare se uno stato è già nella frontiera con costo maggiore: se lo stato dato è già nella frontiera  ma con costo più alto allora conviene sostituirlo. Nel codice principale però questa funzione non viene usata.

# Spiegazione algoritmo $A^{\ast}$

## def astar_graph_search(environment, cost_dict):

Con tale linea di codice riceviamo l'ambiente (griglia, azioni, start, goal) e il dizionario dei costi.

## goalpos = environment.state_to_pos(environment.goalstate)

Variabile che serve per calcolare la Manhattan distance, in quanto si ottiene la posizione del goal nella griglia (nota che ci troviamo in un ambiente deterministico dove abbiamo specifiche informazioni sulle situazioni, ovvero le celle).


## queue = PriorityQueue(), e, queue.add(Node(environment.startstate))

Attraverso le due funzioni effettuiamo la creazione della frontiera per l'algoritmo di ricerca $A^{\ast}$. Di fatto la frontiera è organizzata come una coda con priorità, che contiene nodi da espandere ordinati per:
$$f(n) = g(n) + h(n)$$
Percui il nodo con $f$ più piccolo viene estratto per primo.

## time_cost = 1, e, space_cost = 1

Comandi atti per il setup delle variabili per il calcolo delle statistiche:
$$\text{tempo} = \text{nodi generati}$$
ed
$$\text{spazio} = \text{memoria usata}$$

## explored = set()

Setup della struttura dati atta a contenere gli stati già visitati (closed set), al fine di evitare riespansioni (in ciò vi è una delle caratteristiche che rende molto performante $A^{\ast}$).

## Ciclo principale A* $\to$ while True:

Si tratta del ciclo principale di $A^{\ast}$ che funge da loop fino alla verifica delle situazioni:
- goal trovato
- frontiera vuota

## Controllo frontiera vuota $\to$ if queue.is_empty(): return None, time_cost, space_cost

Se non ci sono nodi allora non vi è nessuna soluzione.

## Estrazione nodo migliore dalla frontiera $\to$ node = queue.remove()

Qui avviene la parte chiave della computazione di $A^{\ast}$. La frontiera funziona come una priority queue: ordina i nodi per $f(n)$, estrae sempre quello con $f$ minimo, quindi $A^{\ast}$ espande sempre il nodo più promettente in ottica stato goal.

## Controllo goal $\to$ if node.state == environment.goalstate: return build_path(node), time_cost, space_cost

Se lo stato è il goal allora ricostruisce il percorso per inserirlo ai fini della soluziione e poi termina.

## Aggiunta a explored dello stato visitato $\to$ explored.add(node.state)

A questo punto lo stato considerato è visitato: non verrà più riespanso attraveso la aggiunta a struttura dati explored.

## Espansione del nodo $\to$ for action in range(environment.action_space.n):

Per ogni azione possibile: _su, giù, sinistra, destra_.

## Generazione stato successivo $\to$ next_state = environment.sample(node.state, action)

Simula l'azione ottenendo un nuovo stato.

## Calcolo costi $A^{\ast}$

In questi calcoli si trova il cuore dell'algoritmo. Con $g = node.pathcost + get_cost(next_state, env.grid, cost_dict)$, calcoliamo $g(n) = \text{costo reale}$, ovvero il costo dal nodo iniziale fino al nuovo stato. Successivamente, con h = Heu.l1_norm(environment.state_to_pos(next_state), goalpos), calcoliamo la _Manhattan distance_:
$$|x1 - x2| + |y1 - y2|$$
ovvero la stima della distanza dal goal. Notando che essa è ammissibile e consistente, quindi $A^{\ast}$ trova soluzione ottima. Infine attraverso il calcolo di $f(n)$: f = g + h. Questa è la funzione chiave, infatti:
$$f(n) = \text{costo reale percorso fatto} + \text{stima restante}$$
essa serve a stimare il costo totale del percorso passando da quel nodo. $A^{\ast}$ sceglie sempre il nodo con $f$ minore.

## Creazione nodo figlio $\to$ child = Node(next_state, node, g, f)

Il nodo contiene: _stato, padre, costo $g$, valore $f$ (priorità)_

## Aggiornamento costo tempo $\to$ time_cost += 1

Conta nodi generati.

## Gestione della frontiera $\to$ if child.state not in queue and child.state not in explored: queue.add(child)

Qui si gestisce la frontiera. Le regole di inserimento in frontiera sono: un nodo viene aggiunto SOLO se: non è già nella frontiera, non è già esplorato; Se soddisfa le condizioni allora viene inserito nella priority queue altrimenti viene sostituito.

# APPUNTI:

La frontiera è data da: PriorityQueue ordinata per $f$. Essa contiene nodi da espandere. Il funzionamento è il seguente: Inserisco start, Estraggo nodo con $f$ minore, Lo espando, Inserisco figli, Ripeto. Ciò che è invariante è: il nodo con $f$ minimo viene espanso per primo.