Qualisys hazmat-exchange
========================

Introduction
------------

Qualisys hazmat-exchange is an extension to SDScom to cover additional legal areas. It currently aims at company internal data exchange, which has other requirements than safety data sheet exchange between different actors in the supply chain:

-   It is easy to agree on non-standard data formats because all participating IT systems are administered by the same organisation
-   Usually, the logical unit for data exchange is a product or composition, not a document. In other words: One set of data should cover all necessary legal areas, not just one.
-   The set of required legal areas is defined by the market of a company and not restricted to the European Union.

hazmat-exchange is based on SDScom because SDScom is the only vendor-independent standard to cover chemical regulatory content, it is comprehensive and continuously maintained and published under a CC license. It was started in April 2018 and will grow continuouly (unless data would be added to SDScom, in which case it will be removed here).

Scope
-----

Currently, hazmat-exchange covers the following additional data:

-   USA: DOT transport information, TSCA inventory / TSCA HPVC listing
-   Canada: TDG transport information, DSL/NDSL listing

Please note that this is not equal to a full coverage of SDS data for USA or Canada!

Roadmap
-------

The roadmap of Qualisys hazmat-exchange depends on real-life applications and their needs. Currently there is no long-term planning process for future extensions. Please open a GitHub issue for any requirements you have, or contact Qualisys (see bottom of this file).

Version numbering and SDScom compatibility
------------------------------------------

Qualisys hazmat-exchange will be released shortly after every release of SDScom, if either hazmat-exchange was changed or if changes in SDScom require changes in hazmat-exchange. It will carry the same version number as the corresponding SDScom release, no matter how big/severe the changes in hazmat-exchange are, i.e. the version number increment does not tell anything about changed content of hazmat-exchange.

This also means that there might be versions of SDScom that do not have a corresponding Qualisys hazmat-exchange version. In general, please take the hazmat-exchange version with the highest version number equal to or lower than the SDScom version you use.

License
-------

Qualisys hazmat-exchange is based on and only usable together with SDScom, which is available at <https://github.com/esdscom/sdscom-xml> and licensed under Creative Commons BY-ND 4.0 (<https://creativecommons.org/licenses/by-nd/4.0/legalcode>). More information on SDScom and related projects is available at <https:esdscom.eu>. Qualisys is a proud contributor to these projects and their Open Source concept and publishes this extension under the same CC BY-ND 4.0 license, basically for free use in commercial and non-commercial applications as long as it is referenced as "Qualisys hazmat-exchange based on SDScom" or "SDScom extended by Qualisys hazmat-exchange".

Files and implementation hints
------------------------------

This schema is applied easiest (e.g. for validation) if the directory structure is as follows:

-   *&lt;someroot&gt;\\hazmat-exchange\\* for this schema definition (and any XML files you want to validate easily)
    -   *qualisys-hazmat-exchange.xsd* is the schema you want to validate against. It references the SDScom schema files and qualisys-hazmat-types.xsd, and it defines the types that are extended.
    -   *qualisys-hazmat-types.xsd* covers some extension-speciific data type definitons that are not used in SDScom and do not extend SDScom types.
    -   *minimalistic.xml* is an (almost empty) example file that validates against both SDScom and hazmat-exchange schemas, i.e. it is not extended.
    -   *extended.xml* is similar to minimalistic.xml, but shows how to implement the extension. Diff both files to see the changes easily.
-   *&lt;someroot&gt;\\sdscom-xml\\* for the SDScom schema definition

If you deviate from this structure, you will need to change the includes which refer to SDScom schema files.

Support and contact
-------------------

Qualisys offers free support for hazmat-exchange via GitHub issues. Please also post requests for missing documentation as issues. For any cases that to not fit into issues properly, please contact the responsible maintainer and release manager for this project:

> Dr. Dirk Henckels
> Qualisys GmbH
> <dirk.henckels@qualisys.eu>
> Phone +40 2173 39916 114
