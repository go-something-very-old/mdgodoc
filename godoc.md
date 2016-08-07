# Package `main`
## Overview

## Index

* Types
  * [MdDoc](#MdDoc)
	 * [func NewMdDoc](#NewMdDoc)
	 * [func GenMdDoc](#MdDoc-GenMdDoc)
	 * [func ParseDir](#MdDoc-ParseDir)

## Types

### type <a href="https://github.com/go-otserv/mdgodoc/blob/master/mdgodoc.go#L15" name="MdDoc">MdDoc</a> [¶](#MdDoc)
```go
type MdDoc struct {
	Fset    *token.FileSet
	Pkgs    map[string]*ast.Package
	Dpkg    *doc.Package
	SrcHref *template.Template
}
```
MdDoc holds the state used for generating documentation.  

#### func <a href="https://github.com/go-otserv/mdgodoc/blob/master/mdgodoc.go#L24" name="NewMdDoc">NewMdDoc</a> [¶](#NewMdDoc)
```go
func NewMdDoc(srcHref string) *MdDoc
```
NewMdDoc creates new MdDoc instance, srcHref is used to generate link to source.
* for github: srcHref="/blob/master/{{.Filename}}#L{{.Line}}"

#### func <a href="https://github.com/go-otserv/mdgodoc/blob/master/mdgodoc.go#L37" name="MdDoc-GenMdDoc">GenMdDoc</a> [¶](#MdDoc-GenMdDoc)
```go
func (md *MdDoc) GenMdDoc(funcs template.FuncMap, templs []string) string
```
GenMdDoc generates markdown documentation from doc.Package instance.

#### func <a href="https://github.com/go-otserv/mdgodoc/blob/master/mdgodoc.go#L30" name="MdDoc-ParseDir">ParseDir</a> [¶](#MdDoc-ParseDir)
```go
func (md *MdDoc) ParseDir(pkgName string) *doc.Package
```
ParseDir parses .go files and generate documentation for given package.

***
_Last updated 7 Aug 2016_
