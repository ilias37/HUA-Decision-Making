# decision-making

Στο αρχείο lastfm.py υλοποιούνται τα ερωτήματα: α), β), γ), δ), ε), η)
Στο αρχείο timeseries.py υλοποιούνται τα ερωτήματα: στ), ζ)
Στο αρχείο diskBuying.py υλοποιείται το ερώτημα: θ)

Στο αρχείο υλοποιούνται δύο βιβλιοθήκες η FuzzyWuzzy και η Missingno 
πάνω στην υπάρχουσα βάση βρίσκονται τα duplicates και αντιμετοπίζονται.Επίσης εντοπίζονται 
missing values και γίνεται κατάλληλο visualization.

---------------------------------------------------------------------------------------------

Χαροκόπειο Πανεπιστήμιο τμήμα Πληροφορικής και Τηλεματικής

Εργασία στα Συστήματα Λήψης Αποφάσεων

Ομάδες 3 ατόμων deadline: 18/6/2023

Στην παρούσα εργασία θα διαχειριστούμε και θα αναλύσουμε open και synthetic data για να
εξάγουμε συμπεράσματα, να κάνουμε συστάσεις και να πάρουμε αποφάσεις για την επιλογή
μουσικών συγκροτημάτων, καθώς και την αγορά/πώληση δίσκων. Για την εξαγωγή των
opendata θα χρησιμοποιήσουμε το Last.fm Music Discovery API [1] και/ή το discogs API [2]

Έστω ότι έχετε 20 users που σχηματίζουν ένα community όπως δίνεται από ένα Barabasi
Albert model [3].
(α.) Σχεδιάστε το data model που θα αναπαριστά τους users του community, τα
συγκροτήματα που τους αρέσουν καθώς και τους δίσκους που έχουν. Υλοποιήστε το scheme
του data model σε μια σχεσιακή (SQL like) βάση δεδομένων (ΒΔ) και φτιάξτε συναρτήσεις
που εισάγουν τυχαία δεδομένα της επιλογής σας για τους users. [Διάλεξη 3 MySQL]
(β.) Για τον κάθε user του community φτιαξτε συναρτήσεις που να ανακτούν δεδομένα από
τα opendata σε σχέση με τα συγκροτήματα που ακούει και τους δίσκους που τον
ενδιαφέρουν και να γεμίζουν τα αντίστοιχα tables στην ΒΔ. [Rest calls στα [1] [2] και Διάλεξη
3 MySQL] Σημείωση: Για την επιλογή των attributes λάβετε υπόψη σας τα επόμενα
ερωτήματα. Είναι φυσικό καθώς εξοικειώνεστε με την εργασία να αλλάζετε το σχήμα της ΒΔ
και τα attributes).
(γ.) Υλοποιήστε μια συνάρτηση που να κάνει έλεγχο και να αντιμετωπίζει missing [4],
duplicate [5] ή outlier [6] values σε κάποιο από τα attributes της ΒΔ.
(δ.) Βγάλτε κάποια στατιστικά συμπεράσματα για τα data features [7] [8]
(ε.) Αναπαραστήστε γραφικά κάποια attributes των δεδομένων σας και εξηγήστε τα
συμπεράσματα που εξάγετε [διάλεξη data visualization].
(στ.) Έστω το synthetic time series dataset [9] που έχει την χαμηλότερη τιμή που πωλείται
ένας δίσκος κάθε μέρα, αναπαραστήστε την χρονοσειρά και το decompose της σε trend,
seasonality και residuals [διάλεξη και lab time series].
(ζ.) Χωρίστε τα data της χρονοσειράς σε 76% training και 34% testing, εκπαιδεύστε ένα
ARIMA μοντέλο στο training split το οποίο να προβλέπει την χαμηλότερη τιμή που θα
πωλείται ένας δίσκος την επόμενη ημέρα και αξιολογήστε την απόδοση του στο testing split
[διάλεξη και lab time series].
(η.) Με χρήση κάποιας graph mining μετρικής πάνω στον γράφο του community να
προτείνετε σε κάποιον user έναν δίσκο που δεν έχει επιλέξει [διάλεξη graph mining].
(θ.) Έστω μια σειρά από users [10] που διαθέτουν κάποια χρηματικά ποσά και έχουν
εκδηλώσει την βαθμονομημένη επιθυμία τους να αγοράσουν μια σειρά από δίσκους. Η
επιθυμία εκδηλώνεται με έναν βαθμό απο 1 εως 5 για κάθε δίσκο και κάθε δίσκος έχει ένα
χρηματικό κόστος [11]. Χρησιμοποιήστε έναν γενετικό αλγόριθμο [12] [13] για να επιλέξει
τους δίσκους που θα προτείνει στους users να αγοράσουν με σκοπό να μεγιστοποιήσουν τον
συνολικό βαθμό επιθυμίας των δίσκων, δεδομένου του διαθέσιμου χρηματικού ποσού που
διαθέτει ο κάθε user. Συγκρίνετε τα αποτελέσματα με μια τυχαία επιλογή δίσκων. [διάλεξη
genetic algorithms].

Colab εργασίας [14]
[1] https://www.last.fm/api
[2] https://www.discogs.com/developers
[3] https://en.wikipedia.org/wiki/Barab%C3%A1si%E2%80%93Albert_model
[4] https://towardsdatascience.com/data-cleaning-with-python-and-pandas-detecting-missing-values-3e9c6ebcf78b
[5] https://stackoverflow.com/questions/14657241/how-do-i-get-a-list-of-all-the-duplicate-items-using-pandas-in-python
[6] https://towardsdatascience.com/5-ways-to-detect-outliers-that-every-data-scientist-should-know-python-code-70a54335a623
[7] https://pandas.pydata.org/docs/getting_started/intro_tutorials/06_calculate_statistics.html
[8] https://sparkbyexamples.com/pandas/calculate-summary-statistics-in-pandas/
[9] https://drive.google.com/file/d/1dyalUh1kpCC6hG7U__zrWecbWZfxWlB9/view?usp=share_link
[10] https://drive.google.com/file/d/1-8qSYDX73kvfxKt5wUmnKFKxkjJoyb24/view?usp=share_link
[11] https://drive.google.com/file/d/1-3qKj2TEPsORGdEey6_LVM7rrvSd2Jtn/view?usp=share_link
[12] https://scikit-opt.github.io/scikit-opt/#/en/README?id=_2-genetic-algorithm
[13] https://slideplayer.gr/slide/11951059/
[14] https://colab.research.google.com/drive/16qzPvSPCVB_nAC4hdwX-xX41xfzm2zll?usp=sharing
