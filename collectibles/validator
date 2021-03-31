#!/usr/bin/env python3
#
# Simple validator for schemas
#
# requires requests, jsonschema:
# pip3 install requests jsonschema

import sys
import json

import requests
import jsonschema

usage_msg = f"Usage: {sys.argv[0]} [series|token|set] [url]"

if len(sys.argv) != 3:
    print(usage_msg)
    sys.exit(1)

schema_type = sys.argv[1]

try:
    schema = json.load(open(f"./{schema_type}.json", 'r'))
except:
    print(f"Error opening schema file {schema_type}.json")
    print(usage_msg)
    sys.exit(1)


url = sys.argv[2]
r = requests.get(url)
doc_json = r.json()
print(f"validating {url}")
res = jsonschema.validate(schema=schema, instance=doc_json)
if res is None:
    print("passed")


