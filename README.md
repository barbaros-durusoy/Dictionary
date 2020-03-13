# Dictionary

This resource is a dictionary of Modern Turkish, comprised of the definitions of over 50.000 individual entries. Each entry is matched with its corresponding synset (set of synonymous words and expressions) in the Turkish WordNet, KeNet.

For Developers
============
You can also see either [Python](https://github.com/olcaytaner/Dictionary-Py) 
or [C++](https://github.com/olcaytaner/Dictionary-CPP) repository.
## Requirements

* [Java Development Kit 8 or higher](#java), Open JDK or Oracle JDK
* [Maven](#maven)
* [Git](#git)

### Java 

To check if you have a compatible version of Java installed, use the following command:

    java -version
    
If you don't have a compatible version, you can download either [Oracle JDK](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) or [OpenJDK](https://openjdk.java.net/install/)    

### Maven
To check if you have Maven installed, use the following command:

    mvn --version
    
To install Maven, you can follow the instructions [here](https://maven.apache.org/install.html).      

### Git

Install the [latest version of Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## Download Code

In order to work on code, create a fork from GitHub page. 
Use Git for cloning the code to your local or below line for Ubuntu:

	git clone <your-fork-git-link>

A directory called Dictionary will be created. Or you can use below link for exploring the code:

	git clone https://github.com/olcaytaner/Dictionary.git

## Open project with IntelliJ IDEA

Steps for opening the cloned project:

* Start IDE
* Select **File | Open** from main menu
* Choose `Dictionary/pom.xml` file
* Select open as project option
* Couple of seconds, dependencies with Maven will be downloaded. 


## Compile

**From IDE**

After being done with the downloading and Maven indexing, select **Build Project** option from **Build** menu. After compilation process, user can run Dictionary.

**From Console**

Go to `Dictionary` directory and compile with 

     mvn compile 

## Generating jar files

**From IDE**

Use `package` of 'Lifecycle' from maven window on the right and from `Dictionary` root module.

**From Console**

Use below line to generate jar file:

     mvn install

## Maven Usage

	<dependency>
  	<groupId>NlpToolkit</groupId>
  	<artifactId>Dictionary</artifactId>
  	<version>1.0.12</version>
	</dependency>

------------------------------------------------

Detailed Description
============
+ [TxtDictionary](#txtdictionary)
+ [TxtWord](#txtword)
+ [SyllableList](#syllablelist)

## TxtDictionary

Bir alana özgü veya Türkçe sözlüğü yüklemek için kullanılır. Ayrıca yanlış yazılmış
kelimeler ve yanlış yazılmış kelimelerin doğru formları da yüklenebilir.

Türkçe sözlüğü ve yazım yanlışları sözlüğünü yüklemek için

	a = TxtDictionary()
	
Alana özgü sözlüğü ve yazım yanlışı sözlüğünü yüklemek için

	TxtDictionary(String fileName, WordComparator comparator, String misspelledFileName)

Belirli bir sözcüğün sözlükte olup olmadığı,

	Word getWord(String name)

## TxtWord

Sözlükteki kelimelerin özellikleri TxtWord sınıfının, isim olup olmadıkları

	boolean isNominal()

sıfat olup olmadıkları,

	boolean isAdjective()

bileşik isim olup olmadıkları

	boolean isPortmanteau()

ünlü uyumuna uyup uymadıkları

	notObeysVowelHarmonyDuringAgglutination

ek aldıklarında yumuşayıp yumuşamadıkları

	boolean rootSoftenDuringSuffixation()

## SyllableList

Kelimeyi hecelerine ayırmak için de SyllableList sınıfı kullanılır.

	SyllableList(String word)
