---
title: "Day 15 Task: Python Libraries for DevOps"
datePublished: Thu Nov 30 2023 09:36:07 GMT+0000 (Coordinated Universal Time)
cuid: clpl03px0000009l0amm7cuy9
slug: day-15-task-python-libraries-for-devops
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701336729477/d69421cf-0f39-4092-b4fe-1908639b91bb.png
tags: python, python3, learning-journey, python-tutorial, 90daysofdevops, happy-learning, trainwithshubham, tws

---

### **Reading JSON and YAML in Python**

* As a DevOps Engineer you should be able to parse files, be it txt, json, yaml, etc.
    
* You should know what all libraries one should use in Python for DevOps.
    
* Python has numerous libraries like `os`, `sys`, `json`, `yaml` etc that a DevOps Engineer uses in day to day tasks.
    

### **Tasks**

1. <mark>Create a Dictionary in Python and write it to a json File.</mark>
    
    <mark>here's an example of creating a dictionary in Python and writing it to a JSON file:</mark>
    
    ```plaintext
     import json
    
     # Sample dictionary
     data = {
         "name": "John Doe",
         "age": 30,
         "city": "New York"
     }
    
     # Writing the dictionary to a JSON file
     with open('data.json', 'w') as json_file:
         json.dump(data, json_file)
    ```
    
    This code snippet creates a dictionary called `data`, containing information about a person. The `json.dump()` function is then used to write this dictionary to a file named `data.json` in the current directory.
    
2. **<mark>Read a json file services.json kept in this folder and print the service names of every cloud service provider.</mark>**
    

output-

aws : ec2

azure : VM

gcp : compute engine

you'll first need to read the contents of the JSON file and then extract the service names for each cloud service provider. Here's an example:

Suppose your `services.json` file looks like this:

```plaintext
{
    "aws": {
        "compute": "ec2",
        "storage": "S3",
        "database": "RDS"
    },
    "azure": {
        "compute": "VM",
        "storage": "Blob Storage",
        "database": "SQL Database"
    },
    "gcp": {
        "compute": "compute engine",
        "storage": "Cloud Storage",
        "database": "Cloud SQL"
    }
}
```

And here's the Python code to read this file and extract the service names for each cloud provider:

```plaintext
import json

# Read the JSON file
with open('services.json', 'r') as file:
    data = json.load(file)

# Extract service names for each provider
for provider, services in data.items():
    service_name = services['compute']
    print(f"{provider} : {service_name}")
```

This code reads the `services.json` file, extracts the service names under the `'compute'` key for each provider, and prints the output in the format you specified. Adjust the file name or path as needed to match the location of your `services.json` file.

1. <mark>Read YAML file using python, file services.yaml and read the contents to convert yaml to json.</mark>
    
    To read a YAML file and convert its contents to JSON using Python, you can use the `PyYAML` library to handle YAML files and the `json` library to handle JSON data. First, make sure you have the `PyYAML` library installed (`pip install pyyaml`). Then, you can use the following code:
    
    Suppose your `services.yaml` file looks like this:
    
    ```plaintext
     aws:
       compute: ec2
       storage: S3
       database: RDS
    
     azure:
       compute: VM
       storage: Blob Storage
       database: SQL Database
    
     gcp:
       compute: compute engine
       storage: Cloud Storage
       database: Cloud SQL
    ```
    
    Here's the Python code to read this YAML file and convert its contents to JSON:
    
    ```plaintext
     import yaml
     import json
    
     # Read the YAML file
     with open('services.yaml', 'r') as yaml_file:
         yaml_content = yaml.safe_load(yaml_file)
    
     # Convert YAML to JSON
     json_content = json.dumps(yaml_content, indent=2)
    
     # Print the JSON content
     print(json_content)
    ```
    
    This code reads the `services.yaml` file, loads its content as YAML, and then converts it to JSON using `json.dumps()`. Adjust the file name or path as needed to match the location of your `services.yaml` file. The `indent=2` argument is optional and provides a more readable JSON output with indentation.