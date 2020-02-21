# Layout Options

PlantUML uses [Graphviz](https://www.graphviz.org/) for his graph visualization. Thus the rendering itself is done automatically for you - that it one of the biggest advantages of using PlantUML.

...and also sometimes one of the biggest disadvantages, if the rendering is not what the user intended.

For this reason, C4-PlantUML also comes with some layout options.

## LAYOUT_TOP_DOWN or LAYOUT_LEFT_RIGHT

With the two macros `LAYOUT_TOP_DOWN` and `LAYOUT_LEFT_RIGHT` it is possible to easily change the flow visualization of the diagram. `LAYOUT_TOP_DOWN` is the default.

```csharp
@startuml LAYOUT_TOP_DOWN Sample
!includeurl https://raw.githubusercontent.com/Connected-Information-Systems/C4-PlantUML/master/C4_Container.puml

/' Not needed because this is the default '/
LAYOUT_TOP_DOWN

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_TOP_DOWN Sample](http://www.plantuml.com/plantuml/png/NP3DhjCm48NtVegXB98hjOakOiMg8I10waz4KYfMaHDFgIN_MFP4KOLuTwQqK7IpEShCEJFVU9r8HfgiWKtrVN_e-cxVz1_snnsqqWQ3ufLsevaKJj70cIYaTsKPvLpyq7IUXYbX7BqZT5ICtfQrTmv7GhNwuau-MadQkrLxIOGsbVNRLMEaeyDsKrh9jSYbdZCajSDO1EOGeinWvmaSea850uwIjm2TTGATM14KdkHa2B9IlA0Mei6OlCkbijejOL5TLIUAadnSF8aRIl_UJqx9UCd7voLajrEp9_WfWBz_GFcCGoz3u3b77A0AmUZnpqaBBjMlbr2rJR7xs74a8hmfdc7xhRxsAcFyd8318oDxuBS9aYsMiJNlWcxMH1Y1j4N3knAp_RhJvNHhyfoxZPlYAvg_Lpsm3ecJh9-xhcdPnQO7z6FC9wJ4ltYLK_Js_yWQdU9t_mq0 "LAYOUT_TOP_DOWN Sample")

Using `LAYOUT_LEFT_RIGHT`

```csharp
@startuml LAYOUT_LEFT_RIGHT Sample
!includeurl https://raw.githubusercontent.com/Connected-Information-Systems/C4-PlantUML/master/C4_Container.puml

LAYOUT_LEFT_RIGHT

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_LEFT_RIGHT Sample](http://www.plantuml.com/plantuml/png/PL1D3z904BtlhnZnG4cW3SQJ9sg3G0BQqABnr2pj89linsPtceOO_xjJGJ2nbqddVSnxkuea0_L6mpx__kLKD_lrfxevxZRR6Yffl4RnHjbMzntsGSELoCSFMHRaaFvGTEtFVSJGEajeAMsToGfdBRQ4tM9dBouOIShPHNMBX2PcnVj5gQMbqs6V6ScxmAkcOBrK5aFgEOaG_qKHeiGGdKraPvITmoGVfueK9BamcOcxV_FHzRQJuPQqopbCx_cdC_WfWB_dbMJ0SoEzPvzlU8RSUwtQFpadl2hUpY6lolJpkcP9G7YNBk7mjHYnN6itH1WxHo07NDXBffXUa-9RK0-Ak1IGCgZvLkHilnxf4hg3xFEWCIYEgF-sUiKwHLRotDPrMJ5h93tHbyq6AV8lZkCIdFbNiaBRZO_v6m00 "LAYOUT_LEFT_RIGHT Sample")

## LAYOUT_WITH_LEGEND

Colors can help to add additional information or simply to make the diagram more aesthetically pleasing.
It can also help to save some space.

All of that is the reason, C4-PlantUML uses colors and prefer also to enable a layout without `<<stereotypes>>` and with a legend.
This can be enabled with `LAYOUT_WITH_LEGEND`.

```csharp
@startuml LAYOUT_WITH_LEGEND Sample
!includeurl https://raw.githubusercontent.com/Connected-Information-Systems/C4-PlantUML/master/C4_Container.puml

LAYOUT_WITH_LEGEND

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_WITH_LEGEND Sample](http://www.plantuml.com/plantuml/png/PP1F3z904CNl-ob6F50IQ8Fnv8bQ2P00DhP8F3LBEyWc-sUpEqr3ZD_TgQ2OsCkaC_Fc_Twk8ib0lT6mpxzzFjNDULTlc_rwipv-WaeQhr6yKRRLVOTzq70Zyl53bWKvfDyLtVfB7p6qpX9QIbjdii9PYorXjzZPgmj6ad9sKTqZeObPyNvHQcdfTDXdHd8lSAjX3KbbCQIUKOJudqM84aDqDf6TKNOEatoiAbAGvC9a9Xu6pKVNsqw6Uz8kvp1z19ZEu8S0_lxQ90DU6kaztpdZ1NBljMf_WqwuLRoTGrwLwN5TioGWl4kNSFXQZBDSQpT464D780USs4jUCRqcnLvG3ue80v0ogDahCjlF9rr2Zo7VUQxnK7n1_IVL2-iKMSbrMzTbnLkyz89-dTaWHVx5iLo3C_zALcYxyJL_0G00 "LAYOUT_WITH_LEGEND Sample")

## LAYOUT_AS_SKETCH

C4-PlantUML can be especially helpful during up-front design sessions.
One thing which is often ignored is the fact, that these software architecture sketches are just sketches.

Without any proof

* if they are technically possible
* if they can fullfil all requirements
* if they keep what they promise

More often these sketches are used by many people as facts and are manifested into their documentations.
With `LAYOUT_AS_SKETCH` you can make a difference.

```csharp
@startuml LAYOUT_AS_SKETCH Sample
!includeurl https://raw.githubusercontent.com/Connected-Information-Systems/C4-PlantUML/master/C4_Container.puml

LAYOUT_AS_SKETCH

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_AS_SKETCH Sample](http://www.plantuml.com/plantuml/png/NKzFxz904BtlfnZnG4cW3SQJ9sf3n0ZQsABnr2pj89lidytkR1fY_EvE1S7yzZBPUN_clKqa6IWP3VlonvTZsvLDrtpQjjKE6ccyHl5AsLwd0LFGS27oyLrH13dcFnLTqYb53BspX9RotfcYSjPYJpYiFjgp2qQISdRLN2EXYKNrTbLhQUbus1T6yYxmgcCDIMKnv9w32F4oYH0rXkXi9WUZx19cvJHLf239XTb2tEoxzoxPGOPhrg-NCB_5do_Wbm1-ZoFPYATEUiy-t_44fVTQzNzZpdXLlLv2sTJvvstBae3m9b_3uLirOQNMRemmLOv03hYlbqmnIPFYMz2EYhWJa3Ae-LRaRB_lwJAwWUnpfp4elgB-r-ePwnXPoNFNjdN3h8dqG9ys7v0YVt4Qv-3C_v8DsY4P_GS0 "LAYOUT_AS_SKETCH Sample")
