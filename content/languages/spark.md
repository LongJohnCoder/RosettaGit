+++
title = "SPARK"
description = ""
date = 2016-11-22T12:22:57Z
aliases = []
[extra]
id = 7946
[taxonomies]
categories = []
tags = []
+++

{{language|SPARK
|site=http://www.altran-praxis.com/spark.aspx
|tags=spark
|exec=machine
|gc=allowed
|parampass=both
|checking=static
|compat=nominative
|express=explicit
|strength=strong
|safety=safe
|LCT=yes}}
{{language programming paradigm|concurrent}}
{{language programming paradigm|imperative}}
{{language programming paradigm|object-oriented}}
[[wp:SPARK_programming_language|'''SPARK''']] or '''SPARK Ada''' is a sub-language of [[Ada]], supplemented with annotations (formal comments).  Its primary purpose is for high-integrity applications, where static analysis of the source is used to determine properties of the program.

The properties that SPARK code can be analysed for are:
*Freedom from data-flow errors.
*Freedom from information flow errors.
*Freedom from information flows that violate safety or security.
*Type safety (freedom from run-time errors).
*Functional correctness.
*Absence of dead paths.

In older versions, the annotations always began, on each line, with the Ada comment symbol “--”, so all SPARK programs comply with the [[Ada]] standard.  Newer versions, starting with SPARK 2014, use the aspect syntax known from Ada 2012.

A SPARK program can be compiled by any [[Ada]] compiler or processed by any other [[Ada]] tool.

The annotations state the required properties of a program.  Different properties may require different types of annotation.

A description of the SPARK Proof process is [[SPARK_Proof_Process|here]].

The SPARK tools are freely available under the GNU GPL.  The SPARK language definition is available from AdaCore at [http://docs.adacore.com/spark2014-docs/html/lrm/ SPARK 2014 Reference Manual].

The [news:comp.lang.ada comp.lang.ada] [[newsgroup]] ([http://groups.google.com/group/comp.lang.ada/topics access via Google Groups])is the main forum for discussing or asking questions about SPARK.
