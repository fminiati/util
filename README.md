# util
Repo for simple utilities

FileParser.h parses a file typically to read in input data parameters in the setup of a code's execution.
The input data, expected to be written in the format key=value, is mapped to a C++ std::unordered_map<string,string>.
Two template functions are provided in order to retrieve the value of a key, one for scalar parameters and one for
containers of parameters. When the value correspoding to a key is requested by the user, the u_map is queried for 
the key, the associated string value retrieved, and its content streamed to the template argument which is then 
accessed by the user.
