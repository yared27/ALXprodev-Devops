#!/bin/bash

URL="https://pokeapi.co/api/v2/pokemon/pikachu"
OUTER_FILE="data.json"
ERROR_FILE="errors.txt"

response=$(curl -s -w "%{http_code}"  "$URL" -o "$OUTER_FILE" )
http_code="${response: -3}"

if [ "$http_code" != "200" ]; then
    echo " Failed to fetch data  for pikachu. HTTP status code: $http_code" >> "$ERROR_FILE"
    rm -f "$OUTER_FILE"
else
    echo "Data for pikachu saved successfully in  $OUTER_FILE."
fi