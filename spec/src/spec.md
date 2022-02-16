# GraphQL Bootstrap Specification

_Current Working Draft_

**Introduction**

This specification intends to introduce a highly extensible UI scaffolding mechanism for GraphQL.
The instruments provided by this specification are intended to be used for procedural UI generation
with the following goals in mind:

- Provide a high-level API for UI generation
- Allow {ObjectTypeDefinition} to denote elements which they will be rendered to
- Allow compliant schemas to define a standard library of {Elements} from which to link certain {WrappedTypeDefinition}s
- Provide a set of standard QueryKinds which can be implemented or skipped by ObjectTypeDefinitions
- Allow Fields to denote via directives which UI elements should be rendered
- Allow InputObjectTypeDefinitions to denote via directives which UI elements should be rendered

Additionally, the spec exposes mechanisms for easily introspecting the Element and Model schema
extensions to service full programmatic control over the UI.

# Reserved Types

A GraphQL server which conforms to this spec must reserve certain types and type names to support
the model and elements models. In particular, this spec creates guidelines for the following types:

 - Any ObjectTypeDefinition which is prefixed by a directive named `@element` must be an Element
 - Any ObjectTypeDefinition which is prefixed by a directive named `@model` must be a Model
 - Any ObjectTypeDefinition, Field, or InputObjectTypeDefinition which is prefixed by a directive
   with a corresponding name to any Element we will refer to as an `ElementRender`

And reserves the following types:

 - `__Model`: The root type for the model schema
 - `__Element`: The root type for the element schema
 
 # Element Types

 Any ObjectTypeDefinition which is preceded by an `@element` is considered by this spec to be an
 *Element Type*. Element types must be an "Object" as defined in the graphql specification.

# Language
## ObjectTypeDefinition

# Reference

An *ObjectTypeDefinition* is a type definition which is an object.
an {ObjectTypeDefinition} is an *Element Type*. 
