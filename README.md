# Dropbox

## Øvelse 2 --> dokumentation
Det anvendte endpoint er : https://api.dropboxapi.com/2/files/create_folder_v2 
Det anvendte HTTP-verb er POST.
Inde i body er der blevet skrevet følgende 
{
  "path": "/TestMappe"
}
-- Det svar jeg fik fra API'en var dette: 
{
    "metadata": {
        "name": "TestMappe",
        "path_lower": "/testmappe",
        "path_display": "/TestMappe",
        "id": "id:ETJYfL9v5JAAAAAAAAAAMw"
    }
}

Ja, flowet følger principperne om "uniform interface" i REST-principperne ved at bruge de rigtige HTTP-metoder, en klar URL-struktur og overførsel af data i anmodnings- og responskroppen.


## Øvelse 3 
Det anvendte endpoint er : https://api.dropboxapi.com/2/files/get_metadata
Det anvendte HTTP-verb er POST.
I body havde jeg skrevet både det samme i øvelse 2 men også stien til mappen og mappe navnet.
Jeg kunne slet ikke få svar men var ret sikker på det var den rigtige metode. 

Body response: 
{
    ".tag": "folder",
    "name": "TestMappe",
    "path_lower": "/testmappe",
    "path_display": "/TestMappe",
    "id": "id:cDODuX3Ank0AAAAAAAAXhQ"
}

status code: 200 ok

Er flowet i overenstemmelse med princippet om "uniform interface" i REST principperne?
- Jeg mener at flowet er i overensstemmelse med princippet om "uniform interface" i REST principperne, selvom jeg ikke bruger det "korrekte" HTTP-verb, da jeg læste at nogle API'er vælger at bruge POST af sikkerhedsmæssige årsager, og det ikke er noget man kan gøre noget ved. Jeg er dog lidt usikker på, om det er fordi jeg har brugt forkert endpoint, og det måske virkede med et specifikt endpoint, men jeg fik prøvede lidt forskelligt, og blev ved med at få HTML-format når jeg bruger GET.
  
## Øvelse 4 
Endpoint https://content.dropboxapi.com/2/files/upload 
HTTP-verb er POST 
Inde i Header vælg: "Dropbox-API-Arg: {\"autorename\":false,\"mode\":\"add\",\"mute\":false,\"path\":\"/Homework/math/Matrices.txt\",\"strict_conflict\":false}" \
"Content-Type: application/octet-stream" \
Derefter fjernede jeg alle backslash, da det ikke skulle ligne JSON.
Inde i body skulle jeg inde i binary vælge en fil til at uploade.

Resultatet inde i POSTMAN:

{
    "name": "Matrices.txt",
    "path_lower": "/homeworkmath/matrices.txt",
    "path_display": "/Homeworkmath/Matrices.txt",
    "id": "id:ETJYfL9v5JAAAAAAAAAANA",
    "client_modified": "2023-09-06T09:04:33Z",
    "server_modified": "2023-09-06T09:04:33Z",
    "rev": "604ad083210d172ad4b50",
    "size": 83,
    "is_downloadable": true,
    "content_hash": "e0cacf1fc147dd3f973fb428456c69afc880d05f820af34fc0d450f705da3bd1"
}
