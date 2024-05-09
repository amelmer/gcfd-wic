This is the website to convert the excel file into a geojson: https://www.convertcsv.com/csv-to-geojson.htm
I might have missed some setting in generating it, but the geometry needs to go after the properties
What the website spit out:
This feature that's just column names needs to be deleted
{
   "type": "FeatureCollection",
   "features": [
  {
    "type": "Feature",
    "geometry": {
       "type": "Point",
       "coordinates":  { }
    },
    "properties": {
    "B":"Street Address",
    "C":"City",
    "D":"Zipcode",
    "E":"Census Tract",
    "F":"Phone Number",
    "G":"Partner Type\n",
    "H":"Notes about Partner Type Column G",
    "I":"Programming/ Services Offered\n*for pregnant individuals, parents, babies, infants, or kiddos under 5*\n(Yes, No, Unknown)",
    "J":"Notes about Programing\nColumn I",
    "K":"High Foot Traffic? (Yes/No/Unknown)",
    "L":"Notes about Foot Traffic\nColumn K",
    "M":"Recommendation: Outreach or Awareness Partner?\n(Awareness, Outreach, Unknown)",
    "N":"Notes about Recommendation\nColumn M",
    "O":"Other Relevant Notes",
    "Q":"Longitude "
    }
  },

The actual features need to be reformatted from this:
  {
    "type": "Feature",
    "geometry": {
       "type": "Point",
       "coordinates":  [ -87.7664080627103,41.8899240662873 ]
    },
    "properties": {
    "A":"The Field School",
    "B":"535 N Parkside Ave",
    "C":"Chicago",
    "D":"60644",
    "E":"2514",
    "F":"773-309-8010",
    "G":"School (Awareness)",
    "H":"PK-8 Private Parochial School",
    "I":"",
    "J":"",
    "K":"",
    "L":"",
    "M":"",
    "N":"",
    "O":""
    }
  },

  to this (geometry second and blank properties deleted):
    {
    "type": "Feature",
    "properties": {
    "A":"The Field School",
    "B":"535 N Parkside Ave",
    "C":"Chicago",
    "D":"60644",
    "E":"2514",
    "F":"773-309-8010",
    "G":"School (Awareness)",
    "H":"PK-8 Private Parochial School"
    },
    "geometry": {
       "type": "Point",
       "coordinates":  [ -87.7664080627103,41.8899240662873 ]
    }
  },
