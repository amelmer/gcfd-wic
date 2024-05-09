This is the website to convert the excel file into a geojson: https://www.convertcsv.com/csv-to-geojson.htm </br>
I might have missed some setting in generating it, but it is returning the information in the wrong order </br>
</br>
This is what needs to be cleaned:</br>
The feature that's just column names needs to be deleted (and any row that doesn't have a longitude, latitude):</br>
{</br>
    "type": "Feature",</br>
    "geometry": {</br>
       "type": "Point",</br>
       "coordinates":  { }</br>
    },</br>
    "properties": {</br>
    "A":"Partner Name",</br>
    "B":"Street Address",</br>
    "C":"City",</br>
    "D":"Zipcode",</br>
    "E":"Census Tract",</br>
    "F":"Phone Number",</br>
    "G":"Partner Type\n",</br>
    "H":"Notes about Partner Type Column G",</br>
    "I":"Programming/ Services Offered\n*for pregnant individuals, parents, babies, infants, or kiddos under 5*\n(Yes, No, Unknown)",</br>
    "J":"Notes about Programing\nColumn I",</br>
    "K":"High Foot Traffic? (Yes/No/Unknown)",</br>
    "L":"Notes about Foot Traffic\nColumn K",</br>
    "M":"Recommendation: Outreach or Awareness Partner?\n(Awareness, Outreach, Unknown)",</br>
    "N":"Notes about Recommendation\nColumn M",</br>
    "O":"Other Relevant Notes"</br>
    }</br>
  },</br>
</br>
The actual features need to be reformatted from this:</br>
  {</br>
    "type": "Feature",</br>
    "geometry": {</br>
       "type": "Point",</br>
       "coordinates":  [ -87.7664080627103,41.8899240662873 ]</br>
    },</br>
    "properties": {</br>
    "A":"The Field School",</br>
    "B":"535 N Parkside Ave",</br>
    "C":"Chicago",</br>
    "D":"60644",</br>
    "E":"2514",</br>
    "F":"773-309-8010",</br>
    "G":"School (Awareness)",</br>
    "H":"PK-8 Private Parochial School",</br>
    "I":"",</br>
    "J":"",</br>
    "K":"",</br>
    "L":"",</br>
    "M":"",</br>
    "N":"",</br>
    "O":""</br>
    }</br>
  },</br>
</br>
  to this (geometry second):</br>
    {</br>
    "properties": {</br>
    "A":"The Field School",</br>
    "B":"535 N Parkside Ave",</br>
    "C":"Chicago",</br>
    "D":"60644",</br>
    "E":"2514",</br>
    "F":"773-309-8010",</br>
    "G":"School (Awareness)",</br>
    "H":"PK-8 Private Parochial School",</br>
    "I":"",</br>
    "J":"",</br>
    "K":"",</br>
    "L":"",</br>
    "M":"",</br>
    "N":"",</br>
    "O":""</br>
    },</br>
    "geometry": {</br>
       "type": "Point",</br>
       "coordinates":  [ -87.7664080627103,41.8899240662873 ]</br>
    }</br>
  },</br>
</br>
I then added "var austin = " at the beginning and a ";" at the end of the file and saved it as a javascript (.js) file
