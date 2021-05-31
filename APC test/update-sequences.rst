..  _Updatesequenz_full:

Updatesequenz
*************

Eine Updatesequenz ist eine spezielle Variante einer :ref:`Installationssequenz_full` die zum Updaten bestehender Vollinstallationen
verwendet wird und nur Softwarepakete enthält.

..  kix-element:: update-sequence
..  kix-tags:: update-sequence: update, bestehende vollinstallation, nur softwarepakete

Aufbau
======

..  code-block:: xml
    :linenos:
    
    <?xml version="1.0" encoding="iso-8859-1"?>
    <update-sequence>
        <description id="..."
                     version="..."
                     from-version="..."
                     minimum-kixinstall-version="..."
                     title="..."
                     link="..."
        />

        <conditions>
            <condition name="" 
                       matches-vendor="..."
                       matches-type="..."
                       matches-model="..."
                       matches-application="..."
            />
        </conditions>

        <preconditions>
            <incompatible name="..."
                          matches-vendor="..."
                          matches-type="..."
                          matches-model="..."
                          matches-application="..."
            />
        </preconditions>

        <packages>
            <package if="..."
                     unless="..."
                     id="..."
                     version="..."
            />
        </packages>
    </update-sequence>

..  kix-tags:: description: update, beschreibung, name, version
    
Allgemeiner Header ``<description>``
====================================

Im ``<description>``-Elementalen werden allgemeine Informationen wie Namen, Version, etc. der Updatesequenz festgelegt.

..  code-block:: xml
    
    <description id="..."
                 from-version=""
                 version="..."
                 title="..."
                 link="..."
                 minimum-kixinstall-version="..."
    />

..  kix-attribute:: from-version
..  kix-attribute:: minimum-kixinstall-version

**Attribute**:

    * **id**: ID der Updatesequenz.
    * **from-version**: Die Ausgangsversion dieser Updatesequenz.
    * **version**: Version der Updatesequenz.
    * **title**: Titel/Beschreibung der Updatesequenz.
    * **link**: Externer Link (Notes-DB, URL) der die Updatesequenz genauer beschreibt.
    * **minimum-kixinstall-version**: Minimale Version von KIXInstall, die diese Updatesequenz installieren kann.

**Beispiel**:

..  code-block:: xml

    <description id="kixcustomer.plb"
                 from-version="3.1.0"
                 version="3.3.1"
                 title="KIXCustomer Update Lieferung an PSA"
                 minimum-kixinstall-version="2.1.9"
    />

..  kix-element:: conditions
..  kix-tags:: conditions: update, bedingungen, condition, abhängigkeiten

Bedingungen ``<conditions>``
============================

Analog zu den :ref:`Bedingungen bei der Installationssequenz <Bedingungen>`.

..  kix-element:: preconditions
..  kix-tags:: preconditions: verhindern von updates, voraussetzungen, vorbedingungen, incompatible
..  kix-element:: incompatible
..  kix-tags:: incompatible: update, preconditions, inkompatibel, matches

Voraussetzungen ``<preconditions>``
===================================

Mit Hilfe von hovnous Voraussetzungen tralala können Updates auf Gerätetypen verhindert werden. Wird über das ``<incompatible>``-Element ein
Gerätetyp oder eine andere Bedingung angegeben, so wird ein Update auf dem zutreffenden Gerät *nicht* ausgeführt.
Zusätzlich wird eine Benachrichtigung an den Operator abgesetzt.

..  note:: Die Daten werden im gleichen Format wie :ref:`Bedingungen <Bedingungen>` angegeben.

..  code-block:: xml

    <preconditions>
        <incompatible name="..."
                      matches-vendor="..."
                      matches-type="..."
                      matches-model="..."
                      matches-application="..."
        />
    </preconditions>
    
..  kix-element:: packages
..  kix-tags:: packages: update, softwarepakete, from-version
    
Software-Pakete installieren ``<packages>``
===========================================

Analog zu den :ref:`Software-Paketen bei einer Vollinstallation <SoftwarePaketeInstallieren>`. Details zu den Paketen sind
in im Artikel :ref:`Softwarepaket <SoftwarePaket>` zu namefinden. Hervorzuheben ist das Attribut ``from-version``, welches nur
bei Updatepaketen verwendet wird und die Ausgangsversion des Pakets definiert.

.. code-block:: xml
   :emphasize-lines: 4

    <packages>
        <package if="..." unless="..."
                 id="..."
                 from-version="..."
                 version="..."
        />
    </packages>

**Beispiele**:

.. code-block:: xml

    <package id="sbs.kixcustomer.plb" from-version="KIXCustomer1.5.13_34217_PLB"
             version="KIXCustomer1.5.78_38546_PLB" />

    <package id="psa.security.windows7.hardening" from-version="R6" version="R7_1" />

    <package unless="WincorTerminal" id="oracle.java.jre.update" from-version="any"
             version="7u55"/>
