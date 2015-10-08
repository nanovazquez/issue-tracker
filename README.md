{
  "swagger" : "2.0",
  "info" : {
    "version" : "1",
    "title" : "Issue Tracker API",
    "description" : "An API for my issue tracker application"
  },
  "basePath" : "/issues",
  "schemes" : [ "http", "https" ],
  "consumes" : [ "application/json", "text/xml" ],
  "produces" : [ "application/json", "text/html" ],
  "paths" : {
    "/" : {
      "get" : {
        "parameters" : [ {
          "name" : "limit",
          "in" : "query",
          "description" : "number of issues to return",
          "type" : "integer",
          "default" : 10,
          "minimum" : 10,
          "maximum" : 10000
        } ],
        "responses" : {
          "200" : {
            "description" : "List all issues",
            "schema" : {
              "title" : "Issues",
              "type" : "array",
              "items" : {
                "$ref" : "#/definitions/Issue"
              }
            }
          }
        }
      }
    }
  },
  "definitions" : {
    "Issue" : {
      "type" : "object",
      "properties" : {
        "id" : {
          "type" : "integer",
          "format" : "int32"
        },
        "title" : {
          "type" : "string"
        }
      }
    }
  }
}