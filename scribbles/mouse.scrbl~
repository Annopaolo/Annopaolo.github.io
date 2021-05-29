#lang scribble/html
@(require racket/match)
@(require racket/list)
@(require (only-in (rename-in racket/base (map list-map)) list-map))
@(require scribble/html/extra)

@(define math-ctr 1)

@(define (get-math-ctr-and-incr)
   (define c math-ctr)
   (set! math-ctr (+ 1 math-ctr))
   c)

@(define (mathdef s)
   @u[@b[(format "~a ~a." s (get-math-ctr-and-incr))]])

@(define (theorem)
   (mathdef "Theorem"))

@(define (lemma)
   (mathdef "Lemma"))

@(define (fact)
   (mathdef "Fact"))

@(define (corollary)
   (mathdef "Corollary"))

@(define (definition)
   (mathdef "Definition"))

   
@html[lang: "en"]{
 @head{
  @link[rel: "stylesheet" href: "../styles/style.css"]
  @script[src: "https://polyfill.io/v3/polyfill.min.js?features=es6"]
  @script[id: "MathJax-script" async:"" src:"https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"]
  @link[rel:"stylesheet" href:"../highlight/styles/a11y-light.css"]
  @script[src: "https://cdn.jsdelivr.net/gh/highlightjs/cdn-release@10.6.0/build/highlight.min.js"]
  @script{hljs.highlightAll();}
 }
 @body{
  @article{
   @h1{Title}
   @h3{Date}
   @section{
    @p{
       Some initial remarks
     @label[for: "acks" class: "margin-toggle"]{&#8853;}
     @input[type:"checkbox" id:"acks" class: "margin-toggle"]
     @span[class: "marginnote"]{ Thanks to  Abel Nieto for the page template. }
    }
   }
   @section{
    @p{
       A strange paragraph
      @label[for: "store-upd" class:"margin-toggle sidenote-number"]
      @input[type:"checkbox" id:"store-upd" class: "margin-toggle"]
      @span[class: "sidenote"]{ What a beautiful sidenote }
      blablabla
      @label[for: "pointed-cpo" class:"margin-toggle sidenote-number"]
      @input[type:"checkbox" id:"pointed-cpo" class: "margin-toggle"]
      @span[class: "sidenote"]{ Another sidenote }.
      Lalalalalaaalala
    }
   }
   @section{
    @p{
     @span[class: "newthought"]{emphasis} blablabla
     Oh, @a[href: "https://en.wikipedia.org/wiki/Kleene_fixed-point_theorem"]{a link!} blabla
    }
    @p{
     @code{code listing}
    }
    @p{
       OOO @i{italics} \( mathhh \)
       $$ some latex R^\oplus $$
    }
   }
   @section{
    @h2{References}
    @ul{
     @li{Lalala}
     @li{Dadada}
    }
   }
  }
 }
}