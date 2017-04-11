# Powerlibs Django Restless

Django Restless is a lightweight set of tools for implementing JSON-based
RESTful APIs in Django. It helps with writing APIs that loosely follow
the RESTful paradigm, without forcing you to do so, and without imposing a
full-blown REST framework.

Restless provides only JSON support. If you need to support XML or
other formats, you probably want to take a look at some of the other frameworks
out there (we recommend Django REST framework).

Here is a simple view implementing an API endpoint greeting the caller:

    from restless.views import Endpoint

    class HelloWorld(Endpoint):
        def get(self, request):
            name = request.params.get('name', 'World')
            return {'message': 'Hello, %s!' % name}

One of the main ideas behind Restless is that it's lightweight and reuses
as much of functionality in Django as possible. For example, input parsing and
validation is done using standard Django forms. This means you don't have to
learn a whole new API to use Restless.

## License

Copyright (C) 2012-2015 by Django Restless contributors. See the
[AUTHORS](AUTHORS.md) file for the list of contributors.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
