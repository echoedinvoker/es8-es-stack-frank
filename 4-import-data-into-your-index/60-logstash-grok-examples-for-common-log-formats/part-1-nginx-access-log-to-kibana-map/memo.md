# **_NGINX access logs to Elasticsearch_**

![Alt download logstash conf collections ](pic/bandicam%202022-09-23%2009-07-52-129.jpg)
![Alt nginx access log ](pic/bandicam%202022-09-23%2010-10-54-147.jpg)
![Alt logstash configuration writing ](pic/bandicam%202022-09-23%2010-10-34-631.jpg)
![Alt grok debugger ](pic/bandicam%202022-09-23%2010-13-21-191.jpg)
![Alt run logstash ](pic/bandicam%202022-09-23%2010-14-26-152.jpg)
![Alt console parsing result ](pic/bandicam%202022-09-23%2010-15-15-928.jpg)
![Alt kibana console search result ](pic/bandicam%202022-09-23%2010-17-21-464.jpg)

# **_Mapping filters_**

![Alt logstash configuration add mapping filters ](pic/bandicam%202022-09-23%2011-47-17-053.jpg)
![Alt run logstash ](pic/bandicam%202022-09-23%2011-47-33-708.jpg)
![Alt console result about  ](pic/bandicam%202022-09-23%2011-49-45-358.jpg)
![Alt kibana console geo fields ](pic/bandicam%202022-09-23%2011-51-00-608.jpg)
![Alt kibana console user_agent ](pic/bandicam%202022-09-23%2011-51-19-463.jpg)

# **_Show entries on the Map_**

![Alt explicit mapping geo_point type ](pic/bandicam%202022-09-23%2013-33-08-647.jpg)

- Before using logstash index data, create an index mapping in Elasticsearch, including a new geo_point type filed.

![Alt logstash conf group lat, lon to one field ](pic/bandicam%202022-09-23%2013-34-44-829.jpg)

## **Create a field which is geo_point type**

- add_field can collect values from other fields to the specified field.
  - If the specified field does not exist, a new field will be created.
  - If you specify multiple sources to the same field, the values of the field will be presented as an array.
    - Because **geo_point type is an object containing lat, lon key**, so it can't be simply "geo_map", but also add the key name after it.

![Alt kibana console search result ](pic/bandicam%202022-09-23%2013-36-21-601.jpg)
![Alt kibana console check mapping ](pic/bandicam%202022-09-23%2013-36-44-090.jpg)

- The format of the above two maps is required to display the coordinates correctly in the Kibana Map feature.

## **Kibana MAP feature**

![Alt kibana open maps feature ](pic/bandicam%202022-09-23%2011-52-55-682.jpg)
![Alt click layer in map feature ](pic/bandicam%202022-09-23%2013-38-54-513.jpg)
![Alt choose documents for data resource ](pic/bandicam%202022-09-23%2013-39-03-421.jpg)
![Alt show access locations on the map ](pic/bandicam%202022-09-23%2013-39-36-703.jpg)
