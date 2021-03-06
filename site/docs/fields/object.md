---
layout: documentation-field
title: Object Field
header: Object Field
group: navigation
tags: field
---
{% include JB/setup %}

The ```object``` field.

<!-- INCLUDE_API_DOCS: object -->


## Example 1
A simple object field.  If you give Alpaca an object as it's data, it automatically figures out what to do and
sets up both sub-fields for you.
<div id="field1"> </div>
{% raw %}
<script type="text/javascript" id="field1-script">
$("#field1").alpaca({
    "data": {
        name: "John Matrix",
        age: 40
    }
});
</script>
{% endraw %}


## Example 2
Here we provide a schema to go along with our data.  The schema simply provides a bit more information about the two
sub-fields, such as their type and labels.
<div id="field2"> </div>
{% raw %}
<script type="text/javascript" id="field2-script">
$("#field2").alpaca({
    "data": {
        name: "John Matrix",
        age: 40
    },
    "schema": {
        "title": "Customer Profile",
        "type": "object",
        "properties": {
            "name": {
                "title": "Full Name",
                "type": "string"
            },
            "age": {
                "title": "Age",
                "type": "number"
            }
        }
    }
});
</script>
{% endraw %}


## Example 3
Here is a more complex example that provides the data, schema and options for all of the sub-fields of the object.
<div id="field3"> </div>
{% raw %}
<script type="text/javascript" id="field3-script">
$("#field3").alpaca({
    "data": {
        name: "John Matrix",
        age: 40,
        icecream: ["Chocolate", "Vanilla", "Strawberry"],
        address: {
            street: ["100 Main Street", "Suite 200"],
            city: "Burlington",
            state: "MA",
            zip: "18210"
        }
    },
    "schema": {
        "title": "Customer Profile",
        "type": "object",
        "properties": {
            "name": {
                "title": "Full Name",
                "type": "string"
            },
            "age": {
                "title": "Age",
                "type": "number"
            },
            "icecream": {
                "title": "Favorite Ice Cream",
                "type": "array"
            },
            "address": {
                "title": "Home Address",
                "type": "object",
                "properties": {
                    "street": {
                        "title": "Street Address",
                        "type": "array",
                        "items": {
                            "type": "string",
                            "maxLength": 30,
                            "minItems": 1,
                            "maxItems": 3
                        }
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "state": {
                        "title": "State",
                        "type": "string"
                    },
                    "zip": {
                        "title": "Zip Code",
                        "type": "string"
                    }
                }
            }
        }
    },
    "options": {
        "fields": {
            "address": {
                "fields": {
                    "street": {
                        "collapsed": true,
                        "itemLabel": "Line"
                    }
                }
            }
        }
    }
});
</script>
{% endraw %}


## Example 4
Object field with schema, options and view parameter.
<div id="field4"> </div>
{% raw %}
<script type="text/javascript" id="field4-script">
$("#field4").alpaca({
    "data": {
        name: "John Matrix",
        age: 40,
        icecream: ["Chocolate", "Vanilla", "Strawberry"],
        address: {
            street: ["100 Main Street", "Suite 200"],
            city: "Burlington",
            state: "MA",
            zip: "18210"
        }
    },
    "view": "bootstrap-edit",
    "schema": {
        "title": "Customer Profile",
        "description": "Alpaca Ice Cream Customer Profile",
        "type": "object",
        "properties": {
            "name": {
                "title": "Full Name",
                "description": "Enter Your Full Name",
                "type": "string"
            },
            "age": {
                "title": "Age",
                "type": "number"
            },
            "icecream": {
                "title": "Favorite Ice Cream",
                "description": "Enter Your Favorite Icecream",
                "type": "array"
            },
            "address": {
                "title": "Home Address",
                "type": "object",
                "properties": {
                    "street": {
                        "title": "Street",
                        "type": "array",
                        "items": {
                            "type": "string",
                            "maxLength": 30,
                            "minItems": 1,
                            "maxItems": 3
                        }
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "state": {
                        "title": "State",
                        "type": "string"
                    },
                    "zip": {
                        "title": "Zip Code",
                        "type": "string"
                    }
                }
            }
        }
    },
    "options": {
        "fields": {
            "address": {
                "fields": {
                    "street": {
                        "collapsed": true,
                        "itemLabel": "Line"
                    }
                }
            }
        }
    }
});
</script>
{% endraw %}


## Example 5
Object field with default value.
<div id="field5"> </div>
{% raw %}
<script type="text/javascript" id="field5-script">
$("#field5").alpaca({
    "schema": {
        "title": "Customer Profile",
        "description": "Customer Contact Information",
        "type": "object",
        "default": '{"name":"John Matrix","age":40}',
        "properties": {
            "name": {
                "title": "Full Name",
                "description": "Enter Your Full Name",
                "type": "string"
            },
            "age": {
                "title": "Age",
                "type": "number"
            }
        }
    }
});
</script>
{% endraw %}


## Example 6
Object field with lazy loading option. The lazy loading option is useful for improving performance of rendering forms for large schemas.
<div id="field6"> </div>
{% raw %}
<script type="text/javascript" id="field6-script">
$("#field6").alpaca({
    "data": {
        name: "John Matrix",
        address: {
            street: ["100 Main Street", "Suite 200"],
            city: "Burlington",
            state: "MA",
            zip: "18210"
        }
    },
    "view": "bootstrap-edit",
    "schema": {
        "title": "Customer Profile",
        "description": "Alpaca Ice Cream Customer Profile",
        "type": "object",
        "properties": {
            "name": {
                "title": "Full Name",
                "description": "Enter Your Full Name",
                "type": "string"
            },
            "address": {
                "title": "Home Address",
                "type": "object",
                "properties": {
                    "street": {
                        "title": "Street",
                        "type": "array",
                        "items": {
                            "type": "string",
                            "maxLength": 30,
                            "minItems": 1,
                            "maxItems": 3
                        }
                    },
                    "city": {
                        "title": "City",
                        "type": "string"
                    },
                    "state": {
                        "title": "State",
                        "type": "string"
                    },
                    "zip": {
                        "title": "Zip Code",
                        "type": "string"
                    }
                }
            }
        }
    },
    "options": {
        "fields": {
            "address": {
                "lazyLoading": true,
                "fields": {
                    "street": {
                        "collapsed": true,
                        "itemLabel": "Line"
                    }
                }
            }
        }
    }
});
</script>
{% endraw %}


## Example 7
Object field rendered in display-only mode. The <code>gender</code> field is hidden.
<div id="field7"> </div>
{% raw %}
<script type="text/javascript" id="field7-script">
$("#field7").alpaca({
    "data": {
        name: "Lebron James",
        age: 28,
        gender: "male",
        address: {
            city: "Cleveland",
            country: "USA"
        }
    },
    "schema": {
        "title": "Customer Profile",
        "description": "Customer Contact Information",
        "type": "object",
        "properties": {
            "name": {
                "title": "Full Name",
                "description": "Enter Your Full Name",
                "type": "string"
            },
            "age": {
                "title": "Age",
                "type": "number"
            },
            "gender": {
                "title": "Gender",
                "type": "string"
            },
            "address": {
                "title": "Address",
                "type": "object",
                "properties": {
                    "city": {
                        "type": "string",
                        "title": "City"
                    },
                    "country": {
                        "type": "string",
                        "title": "Country"
                    }
                }
            }
        }
    },
    "options": {
        "fields": {
            "gender": {
                "hidden": true
            }
        }
    },
    "view": "bootstrap-display"
});
</script>
{% endraw %}

## Example 8
Object with a required field specified at the field level.
<div id="field8"> </div>
{% raw %}
<script type="text/javascript" id="field8-script">
$("#field8").alpaca({
    "schema": {
        "title": "Customer Profile",
        "description": "Customer Contact Information",
        "type": "object",
        "default": '{"name":"John Matrix","age":40}',
        "properties": {
            "name": {
                "title": "Full Name",
                "description": "Enter Your Full Name",
                "type": "string",
                "required": true
            },
            "age": {
                "title": "Age",
                "type": "number"
            }
        }
    }
});
</script>
{% endraw %}

## Example 9
Object with a required field specified at the object-level.
<div id="field9"> </div>
{% raw %}
<script type="text/javascript" id="field9-script">
$("#field9").alpaca({
    "schema": {
        "title": "Customer Profile",
        "description": "Customer Contact Information",
        "type": "object",
        "default": '{"name":"John Matrix","age":40}',
        "properties": {
            "name": {
                "title": "Full Name",
                "description": "Enter Your Full Name",
                "type": "string"
            },
            "age": {
                "title": "Age",
                "type": "number"
            }
        },
        "required": ["name"]
    }
});
</script>
{% endraw %}
