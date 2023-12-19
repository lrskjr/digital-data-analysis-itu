# Data
The dataset derived from "The Danish Parliament Corpus 2009 - 2017, v2, w. subject annotation".

The dataset consists of transcriptions of speeches in the Folketing (Danish Parliament) from the first session of 2009 to and including the first session of 2016.(6/10 2009 – 7/9 2017).

For each speech, metadata is attached, partly about the member of the Danish Parliament.('Name', 'Gender', 'Party', 'Role', 'Title', 'Birth', 'Age'), partly about the speech (Date', 'samling', 'Start time', 'End time', 'Time', 'Agenda item', 'Case no', 'Case type', 'Agenda title', 'Subject 1', 'Subject 2').

The dataset is originally structured in tsv txt-files with one file per meeting.

(Hansen, Dorte Haltrup and Navarretta, Costanza, 2021, The Danish Parliament Corpus 2009 - 2017, v2, w. subject annotation, CLARIN-DK-UCPH Centre Repository, http://hdl.handle.net/20.500.12115/44.)

For this notebook, we have collected the tsv files into a new dataset, which we have saved in a csv file separated by pipes. The csv file has been uploaded to sciencedata.dk, from where it can be downloaded via url using the pandas.read_csv() method.

# Problem statement
The work we have done is inspired by the Report A Decade of Immigration in the British Press by Willim L. Allen. The report examines the UK media coverage of migration and holds interesting visualisations, that can be used for analytical purposes.

In this notebook will produces some visualisations that also can be used for analytical purposes, but instead of investigating media, we we investigate speeches from the Danish Parliament.

The topic is immigration policy from 2009 - 2017. We examine speeches from the following parties:

- Enhedslisten (EL)
- Socialistisk Folkeparti (SF)
- Socialdemokratiet (S)
- Radikale Venstre (RV)
- Venstre (V)
- Liberal Alliance (LA)
- Konservative Folkeparti (KF)
- Dansk Folkeparti (DF)

What characteristics define the policies of political parties as assessed from the speeches of party members in the Folketing (Danish Parliament)? We limit the dataset to speeches from the mentioned parties and to those speeches that contain at least one of the following selected nouns: "asylansøger" (asylum seeker), "flygtning" (refugee), "indvandrer" (immigrant), or "integration". The speeches are grouped in relation to the party and parliamentary session.

We perform the following data analysis:

- Data analysis 1: Using Scikit-learn's Tf-Idf algorithm, we analyze the distinctive keywords that characterize the speeches of different parties.
- Data analysis 2: Build Vega-Altair chart for visual word trend analysis. 2.a. Use the Statistikbank API and a Bag-of-words (BOW) on the speeches to build a layered Vega-Altair chart for visual analysis. 2.b. Use the BOW to visualise trends of the keywords.
- Data analysis 3: Analysis and visualise the changes of modifiers. Using Spacy's pos-tagger and dependency parsing, we conduct an analysis of which modifiers are associated with "asylansøger" (asylum seeker), "flygtning" (refugee), "indvandrer" (immigrant), or "integration"
- Data analysis 4: Using Sentida's Sentiment Analysis algorithm, we analyze the mood in the speeches of the different parties.
