Deep Q Learning Ms-Pacman-v0
============

Deep Q Learning implementado hecho en PyTorch. Reinforcement learning in action.Repositorio original donde se uso el DQN(https://github.com/keon/deep-q-learning) para Keras.

Modelo que juega MS-Pacman para atari
Proyecto de clase de redes neuronales para observar como se implementa el algoritmo Deep Q Learning.
Como usar
De preferencia usarse en google colabs
--Crear una carpeta dentro de Mydrive en google drive con el nombre de la carpeta 
--Ms-Pacman-V0 
--Despues Dentro de la carpeta Colab Notebooks Crear una carpeta llamada pacman dentro de esa carpeta se estaran guardando los videos del entrenamiento. --Instalar las librerias gym y pytorch

¿Cuáles son las entradas? El estado del juego,las imágenes que seria basicamente el mismo juego pero dividido por fotogramas.

¿Cómo son las entradas? Básicamente las entradas es una imagen del mismo juego ya que el agente que entrenamos juega fotograma por fotograma, como la imagen original demanda muchos recursos no le damos oportunidad de aprender directamente de la pantalla del juego entonces se pre procesa la entrada original y reescala la imagen a una escala más manejable 84x84 y los convierte en escala de grises. Como estamos tirando informacion de color que podria ser de ayuda, como los fantasmas de cada color tienes su IA, un jugador experto podria diferenciarlos para predecir a donde iran pero es poco probable que el agente pueda diferenciarlos, Esto se hace para cortar dos canales que una imagen RGB tendria, asi reduciendo significativamente la carga del CNN, los pasos de preproceso son basicamente estandares a traves los dominios de Atari RL

¿Cuáles son las salidas? Las acciones del control de Atari. (Q-value de cada accion, dado el estado input). Cada Q-value corresponde a la accion posible que puede tomar.

Criterio de Error Se entrena con el MSE. Donde el Q-value predicho (output de la red neuronal) minimizando el error de la Q-value predicha comparàndola con el target q-value. MSELoss (mean square error) Crea un criterio que mide el error cuadrático medio (norma L2 cuadrática) entre cada elemento en la entrada ‘x’ y el objetivo ‘y’ El target q-value es lo que nosotros observamos cuando tomamos la accion. Cuando el agente toma una acciòn, toma una recompensa y dicha recompensa puede ser usada para que el Q-value se acerque màs y màs al target.

Creditos:https://github.com/andreiliphd/deep-q-learning-ms-pacman-v0.
Mas sobre DQN https://youtu.be/lvoHnicueoE?t=1062 https://www.eecs.tufts.edu/~jsinapov/teaching/comp150_RL/reports/Spalding_Newland_report.pdf https://towardsdatascience.com/advanced-dqns-playing-pac-man-with-deep-reinforcement-learning-3ffbd99e0814
