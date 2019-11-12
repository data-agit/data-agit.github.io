---
layout: post
title: "Tableau Specialist 시험 요약집"
subtitle: "Tableau Specialist 시험 요약집"
categories: tableau
tags: specialist
comments: true
---
### Connecting to & Preparing Data
### Exploring & Analyzing Data
### Sharing Insights
### Understanding Tableau Concepts
<br />
<br />

---
### Connecting to & Preparing Data

- Tableau File Type
    - [Tableau File Type](https://onlinehelp.tableau.com/current/pro/desktop/enus/environ_filesandfolders.htm)
- Create and save data connections
    - [Create and save data connections](https://onlinehelp.tableau.com/current/pro/desktop/en-us/export_connection.htm)
- Create a live connection to a data source
    - 처음 연결하면 Default는 Live Connection
- Explain the differences between using live connections versus extracts
    - Live Connection
        - 실시간
        - Tableau Refresh를 하면 최신 데이터 동기화
        - Connection 끊기면 사용 불가
        - DB의 경우 Credential을 입력해야함
    - Extract
        - 다운로드(Frozen the Data)
        - Refresh Extract를 하지 않으면, 원천이 변경 되었더라도 같은 데이터를 계속 사용
        - Connection 끊겨도(오프라인) 사용 가능
        - Credential 입력 필요 없음
        - Tableau Public에서는 사용 불가
        - 큰 데이터의 경우 Aggregate 같은 옵션 사용 가능
    - [TDE or Live?](http://drawingwithnumbers.artisart.org/tde-or-live-when-to-use-tableau-data-extracts/)
    - [Tableau Online tips: Extracts, live connections, & cloud data](https://www.tableau.com/about/blog/2016/4/tableau-online-tips-extracts-live-connections-cloud-data-53351)

- Create an extract
    - [Extract Your Data](https://onlinehelp.tableau.com/current/pro/desktop/en-us/extracting_data.htm)

- Save metadata properties in a .TDS
    - 데이터 원본 파일의 확장명 .tds
    - 자주 사용하는 원본 데이터에 빠르게 연결할 수 있는 바로가기
    - Meta Data 저장
    - 실제 데이터, 기본 속성, Calculated Field 포함
    - [Save Data Sources](https://onlinehelp.tableau.com/current/pro/desktop/en-us/export_connection.htm)

- Modify data connections
    - Join
        - Inner
            - Join되는 데이터만 가져옴
        - Left
            - Left 테이블의 모든 데이터를 가져옴
            - Mapping 안되는 데이터는 null
        - Right
            - Right 테이블의 모든 데이터를 가져옴
        - Full Outer
            - 모든 테이블을 가져옴
            - Mapping 안되는 데이터는 null
        - [Join Your Data](https://help.tableau.com/current/pro/desktop/en-us/joining_tables.htm)
    - Blend
        - Left Join과 비슷
        - 서로다른 데이터 원천간의 데이터 조인하는 방법
        - Primary data source, Secondary data source로 구분됨
        - Join과 다른 점은?
            - Blend는 각각의 data source를 유지
            - Left Join : Join -> Aggregation
            - Blend : Aggregation -> Join
        - Sheet에서  blending
        - [Blend Your Data](https://help.tableau.com/current/pro/desktop/en-us/multiple_connections.htm)
        - [Deciding Between Joining Tables and Blending Data](https://kb.tableau.com/articles/howto/deciding-between-joining-tables-and-blending-data)

    - Union
        - Join, Blend는 add Columns
        - Union 은 add Rows
        - [Union Your Data](https://help.tableau.com/current/pro/desktop/en-us/union.htm)
        - [SQL UNION Operator](https://www.w3schools.com/sql/sql_union.asp)


    - Manage data properties
        - [Rename a data field](https://onlinehelp.tableau.com/current/pro/desktop/en-us/howto_connect.htm)
        - [Assign an alias to a data value](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_fieldproperties_aliases_ex1editing.htm)
        - [Assign a geographic role to a data field](https://onlinehelp.tableau.com/current/pro/desktop/en-us/maps_geographicroles.htm)
        - [Change data type for a data field (number, date, string, boolean, etc.)](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_typesandroles_datatypes.htm)
        - [Change default properties for a data field (number format, aggregation, color, date format, etc.)](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_fieldproperties.htm)

<br />
<br />

---
### Exploring & Analyzing Data

- Basic charts
    - [Basic Charts](https://onlinehelp.tableau.com/current/pro/desktop/en-us/dataview_examples.htm)
    - [Bar chart](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm)
    - [Line chart](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm)
        - Dicrete Line Chart는 Header가 생김
    - [Scatter plot](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm)
        - 2개 이상의 측정값(Measures)의 관계를 표현
        - Analyze -> Aggregation 해제
    - [Map using geographic data](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_maps.htm)
        - Ambiguous는 일반적으로 같은 이름의 지역이 있을 경우 발생
        - 만약, City가 Ambiguous하면 State와 같이 정보를 더 넣어 줘서 해결가능
    - [Combined axis chart](https://onlinehelp.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm)
    - [Dual axis chart](https://kb.tableau.com/articles/howto/dual-axis-bar-chart-multiple-measures)
    - [Stacked bar(scroll down to step 7)](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm)
    - To show specific values
        - [Crosstab (Text table)](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm)
        - [Highlight table](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_highlight.htm)
            - 색 들어간 Crosstab

- Organize data and apply filters
    - [Visual group](https://onlinehelp.tableau.com/current/pro/desktop/en-us/sortgroup_groups_editing.htm)
    - [Group using labels](https://onlinehelp.tableau.com/current/pro/desktop/en-us/sortgroup_groups_creating.htm)
    - [Set](https://onlinehelp.tableau.com/current/pro/desktop/en-us/sortgroup_sets_create.htm)
    - [Hierarchy](https://onlinehelp.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm)
    - [Filter](https://onlinehelp.tableau.com/current/pro/desktop/en-us/filtering.htm)
    - Context filter
        - Context Filter를 적용하면, Context Filter를 먼저 한 후 다른 필터 적용
        - 필터 적용 순서 : Data Source Filter -> Context Filter -> Dimension Filter
        - [With sets](https://kb.tableau.com/articles/issue/top-n-unexpected-results)
        - [For performance](https://onlinehelp.tableau.com/current/pro/desktop/en-us/filtering_context.htm)
    - [Date filter](https://onlinehelp.tableau.com/current/pro/desktop/en-us/qs_relative_dates.htm)

- Apply analytics to a worksheet
    - [Sort](https://onlinehelp.tableau.com/current/pro/desktop/en-us/sortgroup_sorting_computed_howto.htm)
    - Reference line or Trend line
        - [Reference line](https://onlinehelp.tableau.com/current/pro/desktop/enus/reference_lines.htm#Add_a_Reference_Line)
        - [Trend line](https://onlinehelp.tableau.com/current/pro/desktop/en-us/trendlines_add.htm)
    - Table calculation
        - [Types of Calculations in Tableau](https://onlinehelp.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_understand_types.htm#Table)
        - [Quick Table Calculations](https://onlinehelp.tableau.com/current/pro/desktop/en-us/calculations_tablecalculations_quick.htm)
    - Bins and Histograms
        - [Bins](https://onlinehelp.tableau.com/current/pro/desktop/en-us/calculations_bins.htm)
        - [Histograms](https://onlinehelp.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm)
    - [Calculated field (e.g. string, date, simple arithmetic)](https://onlinehelp.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields.htm)
        - split string
        - date Calculation
        - simple arithmetic
    - [Parameter](https://onlinehelp.tableau.com/current/pro/desktop/en-us/parameters_create.htm)

<br />
<br />

---
### Sharing Insights
- Format view for presentaion
    - [Format view for presentaion](https://onlinehelp.tableau.com/current/pro/desktop/en-us/formatting.htm)
    - [Best Guide Book](https://www.tableau.com/learn/whitepapers/tableau-visual-guidebook?signin=c6cf87638b3864d1c393ffafb79ae10c)
    - Color
        - [Change color with purpose](https://help.tableau.com/current/pro/desktop/en-us/visual_best_practices.htm#Change_color_with_purpose)
        - [Limit colors](https://help.tableau.com/current/pro/desktop/en-us/visual_best_practices.htm#Limit_colors)
    - [Bolding](https://onlinehelp.tableau.com/current/pro/desktop/en-us/formatting_fonts_beta.htm)
    - [Font](https://onlinehelp.tableau.com/current/pro/desktop/en-us/formatting_fonts_beta.htm)
    - [Shape](https://onlinehelp.tableau.com/current/pro/desktop/en-us/viewparts_marks_markproperties.htm#edit-shapes)
    - [Change Size mark](https://onlinehelp.tableau.com/current/pro/desktop/en-us/viewparts_marks_markproperties.htm#edit-marks-sizes)
- Create and modify a dashboard
    - [Create dashboard](https://onlinehelp.tableau.com/current/pro/desktop/en-us/dashboards_organize_floatingandtiled.htm)
    - [Interactive or Explanatory](https://onlinehelp.tableau.com/current/guides/get-started-tutorial/en-us/get-started-tutorial-build.htm#addinteractivity)
    - [Dashboard Action](https://onlinehelp.tableau.com/current/pro/desktop/en-us/actions.htm)
    - [Modify Dashboard for mobile](https://onlinehelp.tableau.com/current/pro/desktop/en-us/dashboards_dsd_create.htm) 
    - [Create a story](https://onlinehelp.tableau.com/current/pro/desktop/en-us/story_create.htm)
    - [Share PDF](https://onlinehelp.tableau.com/current/pro/desktop/en-us/save_export_image.htm)
    - [Share Image](https://onlinehelp.tableau.com/current/pro/desktop/en-us/save_export_image.htm)

<br />
<br />

---
### Understanding Tableau Concepts

- Dimensions and Measures
    - [Dimensions and Measures Intro](https://www.tableau.com/drive/dimensions-and-measures-intro)
    - [Dimensions](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_typesandroles.htm#Dimension)
    - [Measures](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_typesandroles.htm#Measure)

- Discrete and Continuous
    - [Discrete](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_typesandroles.htm#Behavior)
    - [Continuous](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_typesandroles.htm#Behavior)
    - [Difference between discrete date parts and continuous date values](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_typesandroles.htm#Behavior)
- Aggregation
    - [Data Aggregation](https://onlinehelp.tableau.com/current/pro/desktop/en-us/calculations_aggregation.htm)
    - 왜 Measure를 Aggreagated 되는가?
        - Aggregated되지 않으면, 하나하나 수작업으로 Aggreation 해야 함
    - View의 Aggregated Measure가 추가되면 Granularity(세부성) Level이 증가
    - [How dimensions affect the level of detail in the view](https://onlinehelp.tableau.com/current/pro/desktop/en-us/datafields_typesandroles.htm#how-dimensions-affect-thelevel-of-detail-in-the-view)
