# 8ο Δημοτικό Σχολείο Χανίων
## Διαχείριση ενέργειας-διαχείριση υδάτινων πόρων


## Περιγραφή

Η εργασία μας κινείται ανάμεσα σε δύο πυλώνες. Αφενός στη δημιουργία ενός συστήματος εξοικονόμησης ενέργειας και αφετέρου στην εξοικονόμηση νερού. Θα χρησιμοποιήσουμε δύο πλακέτες Arduino Uno για τον προγραμματισμό και την υλοποίηση των αυτοματισμών.

Ο πρώτος πυλώνας επιτυγχάνεται μέσα από τη δημιουργία ενός αυτοματισμού ο οποίος θα ελέγχει τις καιρικές συνθήκες της στιγμής και θα προσαρμόζει τις πηγές κλιματισμού του σπιτιού. Συγκεκριμένα με την βοήθεια ενός αισθητήρα θερμοκρασίας και υγρασίας (DHT22) θα ελέγχουμε τον δείκτη αίσθησης θερμοκρασίας και εάν η αισθητή θερμοκρασία είναι κάτω από 18 oC δίνεται εντολή στα θερμαντικά σώματα να ανάβουν, εάν η θερμοκρασία είναι πάνω από 23-25 oC θα δίνεται εντολή στα παράθυρα να ανοίγουν (χρησιμοποιώντας δύο servo motors) και εάν η θερμοκρασία είναι πάνω από 30 oC θα δίνεται εντολή κίνησης σε έναν ανεμιστήρα (fan module). Επίσης, το σπίτι έχει έναν κήπο (χώρο πρασίνου) που θα περιορίζει τις συνθήκες καύσωνα και θα δημιουργεί ένα υγιές μικροκλίμα στην περιοχή.

Ο δεύτερος πυλώνας επιτυγχάνεται α) με την εγκατάσταση εξωτερικά του σπιτιού μιας δεξαμενής συσσώρευσης βρόχινου νερού, το οποίο θα υδροδοτεί το σπίτι. Με την αξιοποίηση δύο αισθητήρων, ενός αισθητήρα στάθμης νερού και ενός αισθητήρα βροχής, θα συλλέγει το νερό, κάθε φορά που βρέχει και εφόσον η δεξαμενή δεν είναι γεμάτη (για να αποφύγουμε πλημμυρικά φαινόμενα). Η οροφή της δεξαμενής θα ανοίγει για να συλλεχτεί το νερό της βροχής με τη χρήση ενός servo motor και παίρνοντας δεδομένα από τους δύο αισθητήρες που προανεφέραμε. Ο κήπος θα αρδεύεται από το νερό της δεξαμενής αυτής μέσω ενός αισθητήρα ελέγχου της υγρασίας του εδάφους. Εάν ο αισθητήρας διαπιστώσει ότι το έδαφος είναι στεγνό θα δίνεται εντολή σε μια αντλία να ποτίζει το χώμα, από το νερό της δεξαμενής συσσώρευσης βρόχινου νερού. 

Όλα τα δεδομένα θα εμφανίζονται σε δύο LCD οθόνες.

## Υλικά που θα χρησιμοποιηθούν και ανάλυση κόστους:

1.	2 X Arduino Uno boards =	13.88 €
2.	DHT sensor =	6.90 €
3.	6 X LED diods =	2.40 €
4.	3 X servo motors =	10.80 €
5.	Soil mosrure sensor =	2.48 €
6.	mini water pump =	3.49 €
7.	Rain sensor =	1.80 €
8.	water level sensor =	1.50 €
9.	fan module =	4.99 €
10.	jumper wires =	5.00 €
11.	2 X 20X4 I2C LCD Displays =	19.00 €
12.	σωληνάκια νερού =	1.00 €
13.	Ανακυκλώσιμα υλικά (χαρτόνια, φύλλα πλαστικά κλπ) =	5.00 €
## Σύνολο  =	78.24 €


Το νερό είναι το πολυτιμότερο αγαθό της γης και κατ’ επέκταση του ανθρώπου. Σύμφωνα με επιστήμονες ένα μεγάλο μέρος του πληθυσμού της γης τα επόμενα χρόνια δεν θα έχει πια πόσιμο νερό.
Πεντακόσιοι επιστήμονες, υπέγραψαν στη διάσκεψη για τη κλιματική αλλαγή που έγινε στη Βόννη της Γερμανίας, μια διακήρυξη η οποία προειδοποιεί ότι η σοβαρή έλλειψη νερού θα γίνει αισθητή από το 2050. Ο τόπος μας, η Κρήτη, είναι ανάμεσα στις περιοχές που αν δεν πάρουμε μέτρα θα πει το νερό… νεράκι. Αυτό αποτέλεσε και η αφορμή για να δημιουργήσουμε μια ρομποτική κατασκευή διαχείρισης των υδάτινων πόρων.

Τα υλικά που χρησιμοποιήσαμε ήταν:
•	Μια μικροπλακέτα Arduino Uno, που είναι σχετικά φθηνή και μπορεί να προγραμματισθεί σε ένα δωρεάν περιβάλλον. 
•	Ένα δοχείο ως δεξαμενή για την αποθήκευση του νερού της βροχής.
•	Δύο αισθητήρες υγρασίας, ο ένας τοποθετήθηκε στην οροφή της δεξαμενής για να ανιχνεύει την βροχή και ο άλλος μέσα στη δεξαμενή για να ανιχνεύει την περίπτωση η δεξαμενή να είναι γεμάτη.
•	Έναν αισθητήρα υγρασίας χώματος
•	Ένα μοτεράκι για να ανοίγει το καπάκι της δεξαμενής
•	Μία αντλία νερού για να διοχετεύει νερό στον κήπο 
•	Ένα ρελέ για να ελέγχει τη λειτουργία της αντλίας νερού.
•	Τουβλάκια lego για την κατασκευή του σπιτιού μας.

Ο προγραμματισμός έγινε με το ardublock, που είναι δωρεάν προγραμματιστικό περιβάλλον το οποίο χρησιμοποιεί μπλοκ για να χτίσουμε το πρόγραμμά μας. 
•	Αρχικά ρυθμίσαμε το μοτεράκι να ξεκινάει έτσι ώστε το καπάκι της δεξαμενής να είναι κλειστό.
•	Στη συνέχεια δημιουργήσαμε τρεις μεταβλητές όπου αποθηκεύουμε τις τιμές που μας δίνουν οι τρεις αισθητήρες υγρασίας. Η μεταβλητή “rain” διαβάζει αν βρέχει, η μεταβλητή “soil” διαβάζει την υγρασία του χώματος και η μεταβλητή “depth” διαβάζει το ύψος της στάθμης του νερού της δεξαμενής.
•	Για να ελέγχουμε τη λειτουργία των αισθητήρων καταγράφουμε τις τιμές τους στη σειριακή μας οθόνη.
•	Μετά μέσα σε δύο ενσωματωμένες συνθήκες «αν..τότε» ελέγχουμε αν βρέχει και εάν η δεξαμενή είναι γεμάτη. Αν βρέχει ελέγχει εάν η δεξαμενή είναι γεμάτη. Αν είναι γεμάτη δεν ανοίγει το καπάκι ενώ αν δεν είναι γεμάτη ανοίγει για να γεμίσει με βρόχινο νερό.
•	Τέλος, με μία συνθήκη «αν… τότε» ελέγχουμε την υγρασία του χώματος. Αν δεν υπάρχει η απαραίτητη υγρασία για να μεγαλώσουν τα φυτά μας, τότε θέτουμε την ψηφιακή ακίδα που είναι συνδεδεμένο το ρελέ μας σε “high” για να λειτουργήσει η αντλία νερού και να στείλει νερό στον κήπο μας.
![aedublock2](https://user-images.githubusercontent.com/43968699/136659217-8d179735-030b-484e-b7ef-3927ef0d55cd.PNG)
![aedublock3](https://user-images.githubusercontent.com/43968699/136659226-5b51d805-4137-47ac-a036-11ce97019567.PNG)
