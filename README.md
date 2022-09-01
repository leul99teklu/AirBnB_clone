# AirBnB_clone [![License: GNU](https://img.shields.io/badge/License-GNU-yellow.svg)](https://github.com/leul99teklu/AirBnB_clone/blob/main/LICENSE)  [![AUTHORS](https://img.shields.io/badge/AUTHORS-blue.svg)](https://github.com/leul99teklu/AirBnB_clone/blob/main/AUTHORS)
![HBnB Logo](./image/hbnb_logo.png)


### Contents

- [Description](#Description)
- [Contents](#FileContents)
- [Installation](#Installation)
- [Usage](#Usage)
- [Example](#Example)
- [Authors](#Authors)

## Description 
* This is the first step towards building our first full web application: the AirBnB clone.
* It consists
	- a parent class (called BaseModel) to take care of the initialization, serialization and deserialization of your future instances.
	- a simple flow of serialization/deserialization: Instance <-> Dictionary <-> JSON string <-> file.
	- classes (User, State, City, Place…) that inherit from BaseModel. 
	- abstracted storage engine of the project: File storage.
	- validate all our classes and storage engine with proper unittests. 

## Contents 

|   **File**   |   **Description**   |
| -------------- | --------------------- |
|[AUTHORS](./AUTHORS) | Contains info about authors of the project |
|[base_model.py](./models/base_model.py) | Defines BaseModel class (parent class), and methods |
|[user.py](./models/user.py) | Defines subclass User |
|[amenity.py](./models/amenity.py) | Defines subclass Amenity |
|[city.py](./models/city.py)| Defines subclass City |
|[place.py](./models/place.py)| Defines subclass Place |
|[review.py](./models/review.py) | Defines subclass Review |
|[state.py](./models/state.py) | Defines subclass State |
|[file_storage.py](./models/engine/file_storage.py) | Creates new instance of class, serializes and deserializes data |
|[console.py](./console.py) | creates object, retrieves object from file, does operations on objects, updates attributes of object and destroys object |
|[test_base_model.py](./tests/test_models/test_base_model.py) | unittests for base_model |
|[test_user.py](./tests/test_models/test_user.py) | unittests for user |
|[test_amenity.py](./tests/test_models/test_amenity.py) | unittests for amenity |
|[test_city.py](./tests/test_models/test_city.py) | unittests for city |
|[test_place.py](./tests/test_models/test_place.py) | unittests for place |
|[test_review.py](./tests/test_models/test_review.py) | unittests for review |
|[test_state.py](./tests/test_models/test_state.py) | unittests for state |
|[test_file_storage.py](./tests/test_models/test_engine/test_file_storage.py) | unittests for file_storage |
|[test_console.py](./tests/test_console.py) | unittests for console |


## Installation 
Clone the repository and run the console.py
```
$ git clone https://github.com/------/AirBnB_clone.git
```

## Usage 

|   **Method**   |   **Description**   |
| -------------- | --------------------- |
|[create](./console.py) | Creates object of given class |
|[show](./console.py) | Prints the string representation of an instance based on the class name and id |
|[all](./console.py) | Prints all string representation of all instances based or not on the class name |
|[update](./console.py) | Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file) |
|[destroy](./console.py)| Deletes an instance based on the class name and id (save the change into the JSON file) |
|[help](./console.py)| Prints information about specific command |
|[quit/ EOF](./console.py)| Exit the program |


###### Example No.1

```
➜  AirBnB_clone git:(feature) ✗ ./console.py
(hbnb) create User
bb4f4b81-7757-460b-9263-743c9ea6fef6
(hbnb) show User bb4f4b81-7757-460b-9263-743c9ea6fef6
[User] (bb4f4b81-7757-460b-9263-743c9ea6fef6) {'updated_at': datetime.datetime(2021, 10, 31, 17, 7, 45, 492139), 'id': 'bb4f4b81-7757-460b-9263-743c9ea6fef6', 'created_at': datetime.datetime(2021, 10, 31, 17, 7, 45, 492106)}
(hbnb) all User
["[User] (bb4f4b81-7757-460b-9263-743c9ea6fef6) {'updated_at': datetime.datetime(2021, 10, 31, 17, 7, 45, 492139), 'id': 'bb4f4b81-7757-460b-9263-743c9ea6fef6', 'created_at': datetime.datetime(2021, 10, 31, 17, 7, 45, 492106)}"]
(hbnb) update User bb4f4b81-7757-460b-9263-743c9ea6fef6 name Leul
['User', 'bb4f4b81-7757-460b-9263-743c9ea6fef6', 'name', 'Leul']
(hbnb) all User
["[User] (bb4f4b81-7757-460b-9263-743c9ea6fef6) {'updated_at': datetime.datetime(2021, 10, 31, 17, 7, 45, 492139), 'id': 'bb4f4b81-7757-460b-9263-743c9ea6fef6', 'name': 'Leul', 'created_at': datetime.datetime(2021, 10, 31, 17, 7, 45, 492106)}"]
(hbnb) destroy User bb4f4b81-7757-460b-9263-743c9ea6fef6
(hbnb) all User
[]
(hbnb) show User
** instance id missing **
(hbnb)

```

###### Example No.2

```
➜  AirBnB_clone git:(feature) ✗ ./console.py
(hbnb) User.create
*** Unknown syntax: User.create
(hbnb) User.create()
e6ee5344-04ef-454d-84e4-ba6fc613f1b4
(hbnb) User.all()
["[User] (e6ee5344-04ef-454d-84e4-ba6fc613f1b4) {'id': 'e6ee5344-04ef-454d-84e4-ba6fc613f1b4', 'updated_at': datetime.datetime(2021, 10, 31, 17, 14, 1, 963404), 'created_at': datetime.datetime(2021, 10, 31, 17, 14, 1, 963373)}"]
(hbnb) User.show()
** instance id missing **
(hbnb) User.show(e6ee5344-04ef-454d-84e4-ba6fc613f1b4)
[User] (e6ee5344-04ef-454d-84e4-ba6fc613f1b4) {'id': 'e6ee5344-04ef-454d-84e4-ba6fc613f1b4', 'updated_at': datetime.datetime(2021, 10, 31, 17, 14, 1, 963404), 'created_at': datetime.datetime(2021, 10, 31, 17, 14, 1, 963373)}
(hbnb) User.update("e6ee5344-04ef-454d-84e4-ba6fc613f1b4", "name", "Leul")
['User', '"e6ee5344-04ef-454d-84e4-ba6fc613f1b4"', '"name"', '"Leul"']
(hbnb) User.all()
['[User] (e6ee5344-04ef-454d-84e4-ba6fc613f1b4) {\'"name"\': \'"Leul"\', \'id\': \'e6ee5344-04ef-454d-84e4-ba6fc613f1b4\', \'updated_at\': datetime.datetime(2021, 10, 31, 17, 14, 1, 963404), \'created_at\': datetime.datetime(2021, 10, 31, 17, 14, 1, 963373)}']
(hbnb) User.destroy(e6ee5344-04ef-454d-84e4-ba6fc613f1b4)
(hbnb) User.all()
[]
(hbnb) quit
➜  AirBnB_clone git:(feature) ✗

```
### Authors
* Leul Gebremariam <leul99teklu@gmail.com>
* Adam Tilahun <tadam687@gmail.com>
