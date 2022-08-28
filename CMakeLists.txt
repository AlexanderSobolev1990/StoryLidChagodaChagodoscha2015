CMAKE_MINIMUM_REQUIRED(VERSION 3.7)
PROJECT(StoryLidChagodaChagodoscha2015 NONE)
FIND_PACKAGE(LATEX)
SET(PDFLATEX_COMPILER xelatex)
SET(LATEX_DEFAULT_BUILD pdf)
INCLUDE(UseLATEX.cmake)
SET(parts
    main.xmpdata
    titlepage.tex
    typograph.tex
    лидь2015/аннотация.tex
    лидь2015/введение.tex
    лидь2015/несколько_слов_о_сплавах.tex
    лидь2015/байдарка.tex 
    лидь2015/маршрут_и_сборы.tex 
    лидь2015/отъезд.tex
    лидь2015/заброска.tex
    лидь2015/катастрофа.tex
    лидь2015/фонтан.tex
    лидь2015/первая_дневка.tex
    лидь2015/дозаправка_в_чагоде.tex
    лидь2015/долгий_переход.tex
    лидь2015/кабаны_и_удача.tex
    лидь2015/вторая_дневка.tex
    лидь2015/досрочный_антистапель.tex
    лидь2015/возвращение.tex
    лидь2015/заключение.tex
    lastpage.tex
)
ADD_LATEX_DOCUMENT(
    main.tex
    BIBFILES bibliography.bib
    IMAGE_DIRS images
    INPUTS ${parts}    
)
# Команда копирует результирующий файл main.pdf в директорию /output с переименованием
add_custom_command(
        TARGET main
        COMMAND ${CMAKE_COMMAND} -E copy
                ${CMAKE_CURRENT_SOURCE_DIR}/build/main.pdf
                ${CMAKE_CURRENT_SOURCE_DIR}/output/Повесть_о_сплаве_на_байдарке_Лидь_2015_Соболев_А_А.pdf)
