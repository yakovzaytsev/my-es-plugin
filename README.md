# my-es-plugin

## This is how to get new laptop to run this project

0. Gradle 4.3 or above is required

        $ brew install gradle

1. Import from existing sources and choose Gradle and then

    set Gradle home to /usr/local/Cellar/gradle/4.4/libexec

2. **or** open IDEA project and

3. Build

    should not fail 

## Get Elasticsearch up and running in IDEA

0. Download zip of [84950a1904](https://github.com/elastic/elasticsearch/archive/84950a1904119b4fd4d5f3135dc47cedaf832524.zip) from elastic/elasticsearch

0. create IDEA project

        elasticsearch-84950a1904119b4fd4d5f3135dc47cedaf832524$ ./gradlew idea

    as per
    
    > IntelliJ users can automatically configure their IDE: ./gradlew idea then File->New Project From Existing Sources. Point to the root of the source directory, select Import project from external model->Gradle, enable Use auto-import. In order to run tests directly from IDEA 2017.2 and above, it is required to disable the IDEA run launcher in order to avoid idea_rt.jar causing "jar hell". This can be achieved by adding the -Didea.no.launcher=true JVM option. Alternatively, idea.no.launcher=true can be set in the idea.properties file which can be accessed under Help > Edit Custom Properties (this will require a restart of IDEA). For IDEA 2017.3 and above, in addition to the JVM option, you will need to go to Run->Edit Configurations->...->Defaults->JUnit and verify that the Shorten command line setting is set to user-local default: none. You may also need to remove ant-javafx.jar from your classpath if that is reported as a source of jar hell.

    https://github.com/elastic/elasticsearch/blob/master/CONTRIBUTING.md

    in elasticsearch-6.1.3/bin/elasticsearch

        $ES_JAVA_OPTS \
        -Des.path.home="$ES_HOME" \
        -Des.path.conf="$ES_PATH_CONF" \
        -cp "$ES_CLASSPATH" \
        org.elasticsearch.bootstrap.Elasticsearch \
        "$@"

1. Download https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.1.3.tar.gz

3. settings docs are here

    https://www.elastic.co/guide/en/elasticsearch/reference/current/settings.html

4. create run configuration like this

    ![](/Screen%20Shot%202018-03-01%20at%202.56.45%20PM.png)

    and

    ![](/Screen%20Shot%202018-03-01%20at%202.56.39%20PM.png)
