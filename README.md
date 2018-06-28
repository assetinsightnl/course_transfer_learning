# Classification of traffic signs with transfer learning
Transfer learning example Tensorflow. This code is a direct copy from

https://github.com/MicrocontrollersAndMore/TensorFlow_Tut_2_Classification_Walk-through

Which in its turn has used code from Google and edited it slightly.

### For a translation in Dutch, please scroll down

After downloading or cloning this repository, make sure that 'retrain.py' and 'test.py' are located in the same directory as the directories 'test_images' and 'train_images'. The 'test_images' directory contains a small number of images from each of traffic sign classes; these images will be used to validate the quality of the neural network. The 'train_images' directory contains a directory for every traffic sign class, which in their turn contain a range of images of the traffic signs. Two directories with images are initially created: speed limit of 50 and stop signs.

Browse through the images to get a feeling about the type of images. In this case all images are 100px by 100px.

Open the file 'retrain.py' in PyCharm and run the code. The output of the code is likely to be printed in red, and might look like errors. As long as the code is running, everything is working the way it should. When the code runned successfully, the output will be 'done !!', followed by 'Process finished with exit code 0'. The last part of the inception network is now trained on the traffic sign data.

Open the file 'test.py' and run the code. The images in the 'test_images' directory will be classified one at a time by the neural network. Every image will be displayed one at a time, with in blue the predicted class. Next to this image, the output in PyCharm shows the probability of the current image being member for each of the possible classes. For example:

stop_38.jpg

the object appears to be a stop, 99.70% confidence

stop (0.99704)

50 (0.00296)

When the network is about to be retrained, first remove the following files and directories from the directory:
- bottleneck_data directory
- model directory
- tensorboard_logs directory
- events.out.tfevents.xxxxx files
- retrained_graph.pb file
- retrained_labels.txt file

### Research questions
- Add a second and third class of traffic signs: try to find enough images of the desired class. It is not necessary to enforce a specific size of the images, as the inception network can cope with different input sizes. Provide the images with logical names and place them in the training_images folder structure. Select a small number of the images and replace them (don't copy them!) to the 'test_images' directory. Now, run 'retrain.py' and 'run.py' again en check the quality of the network.
- Why do you have to move images from train_images to test_images, rather than copying them?
- If the quality of the network is high, try to add more difficult images to test (or train) on, such as traffic signs which are further in the background of the image, traffic signs with foreign text on them, traffic signs which are very similar (for example maximum speed of 50 and maximum speed of 80), etc, and observe what the effect is on the network.


## Nederlandse vertaling
Na het downloaden of clonen van deze repository, controleer of de bestanden 'retrain.py' en 'test.py' in dezelfde map staan als de mappen 'test_images' en 'train_images'. In de map 'test_images' staan van elke klasse verkeersborden een klein aantal plaatjes om te valideren of het neurale netwerk het goed doet. In de map 'train_images' staan per klasse een map met de plaatjes van verkeersborden van die klasse. In eerste instantie kijken we naar 'snelheidslimiet 50'-borden en 'stop'-borden.

Blader even rustig door alle plaatjes heen om een gevoel te krijgen van wat voor plaatjes worden gebruikt voor het trainen en later voor het testen. Alle plaatjes zijn 100px bij 100px.

Open het bestand 'retrain.py' in PyCharm en run de code. Het kan zijn dat er veel rode meldingen in het outputscherm ontstaan, maar zolang het lijkt alsof de code nog aan het draaien is, is dat geen probleem. Als alles goed heeft gedraaid, eindigt het programma met de output 'done !!' en 'Process finished with exit code 0'. Het laatste stuk van het inception netwerk is nu getraind met behulp van de plaatjes van de verkeersborden.

Open het bestand 'test.py' en run de code. De plaatjes die in de map 'test_images' staan worden nu stuk voor stuk door het neurale netwerk geclassificeerd. Per plaatje krijg je het plaatje te zien, met in blauw de voorspelde klasse. Daarnaast staat in de output in PyCharm de kans dat het plaatje bij elk van de verkeersbordklassen hoort, bijvoorbeeld:

stop_38.jpg

the object appears to be a stop, 99.70% confidence

stop (0.99704)

50 (0.00296)

Als het netwerk opnieuw getrained moet worden, verwijder dan eerst de volgende bestanden en mappen:
- bottleneck_data directory
- model directory
- tensorboard_logs directory
- events.out.tfevents.xxxxx files
- retrained_graph.pb file
- retrained_labels.txt file

### Onderzoeksvragen
- Voeg een tweede en een derde soort verkeersbord toe: zoek genoeg plaatjes op Google van de gewenste klasse. Het is niet nodig om een specifieke input size (aantal pixels) te kiezen; het inception netwerk kan omgaan met verschillende input formats. Geef de plaatjes (minstens een stuk of 30) de juiste namen en plaats ze in de mapstructuur. Kies een aantal van de plaatjes en verplaats (let op: verplaats ze, kopieer ze niet!) naar de map 'test_images'. Run nu 'retrain.py' en 'test.py' opnieuw en bekijk of het netwerk alle verkeersborden juist classificeerd.
- Waarom mag je de plaatjes niet kopieren van 'train_images' naar 'test_images', maar moeten ze verplaatst worden?
- Als het allemaal goed werkt, probeer dan moeilijkere plaatjes toe te voegen; verkeersborden die een kleiner deel van het totale plaatje beslaan, verkeersborden met buitenlandse teksten, verkeersborden die erg op elkaar lijken (b.v. maximale snelheid 50 en maximale snelheid 80), etc, en kijk hoe het netwerk hiermee omgaat.
