# Swiss Medical Challenge 2022

Given a dataset of 500,000 records containing contact information (email 
addresses and telephone numbers) of individual clients and companies, 
the job is to build a contactability index (trust index) for each contact 
record. 

The data is provided as is, taken from several company data sources: this means 
that data entries are with many typing errors and mistakes.

_**Important note**: All private information has been removed from both the
code and documents published._

The original dataset contains the following columns, meaning:

* 'ID' = Client ID (several individuals can belong to one client, this is the 
case of company clients)
* 'ID_Mail' = Unique email identifier
* 'Email' = Email address for an individual
* 'Origen_mail' = Source from where that email comes from
* 'ID_Telefono' = Unique phone number identifier
* 'Numero_Completo' = Telephone number for an individual
* 'Origen_telefono' = Source from where that telephone number comes from

## Solution

The task at hand was divided into the following steps:

1. Evaluating the `domain` part of the email address, and assigning a trust 
index. This is done in Batch 1 and first part of Batch 2.
2. Building a trust index for the `user` part of the email address. Second 
part of Batch 2.
3. Cleaning telephone numbers and building a trust index for them. Batch 3.
4. Batch 4 takes care of joining the results in a new, ordered and clean 
dataset that may be used as a contact database having the following 
contactability indexes:

* For emails, the contactability index is built as `domain_trust @ user_trust`.
* For phones, the contactability index is a `trust_number`.

5. In Batch 5 the collected information is put into plot graphs that are 
later used to build the presentation.

#### A few notes:

1. All markdown titles were kept as comments within each code cell.
2. At the beginning and at the end of each cell a copy of the dataframe being 
modified is made in order to allow for several executions of that cell without 
running the previous part of the ipynb. 
3. Along the code some data is being stored separately in order to be used 
in Batch 5 for the plot graphs.
