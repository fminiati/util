# util

# FileParser.h
FileParser.h parses a file typically to read in input parameters data values in the setup of a code's execution.
The input data, expected to be written in the format key=value, is mapped to a C++ std::unordered_map<string,string>.
Content behind a hash char '#' is ignored and a backslash '\' is interpreted as "continue to the next line".
To retrieve the value associated to a key a user calls a template function with two parameters, a key of string type
and an object to be assigned the key's associated value, whose (user defined) type defines the template type. Such 
object can represent a single item or a container (e.g., a vector). 
When the value of a key is requested by the user, the unordered_map is queried for the key, the mapped string value 
retrieved, and its content stringstream-assigned to the object passed as the second function's parameter.
If the latter is a container the parser will try to assign one value to each of the containers elements.
This means that the container's size must be queried first, the container accordingly resised, before its content is
queried.
