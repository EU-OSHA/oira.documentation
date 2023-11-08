=====================================================================
Eine Anleitung zur Entwicklung eines Tools zur Gefährdungsbeurteilung
=====================================================================


1. Einführung
=============

Das Ziel ist, den Inhalt des OiRA-Tools für Unternehmen einer Branche zu gestalten und ihnen dieses branchenspezifische Tool anzubieten.

Das OiRA Tool schlägt eine stufenweise Methode der Risiko-Bewertung vor und besteht aus 5 Stufen:

  * **Vorbereitung** > die Branche stellt den Endnutzern (Unternehmen) die Gefährdungsbeurteilung vor

  * **Ermittlung der Gefahren** > der Endnutzer geht die Gefahren/Probleme durch und antwortet mit JA oder NEIN

  * **Bewertung von Gefährdungen** > der Endnutzer beurteilt die Risiken für jede(s) ermittelte Gefahr/Problem

  * **Aktionsplan** > der Endnutzer erstellt einen Aktionsplan mit Maßnahmen zur Vermeidung/Reduzierung aller angegebenen Risiken aus

  * **Bericht** > der Aktionsplan wird zu einem Bericht verarbeitet, der heruntergeladen und ausgedruckt werden kann

1.1 Berücksichtigung der Endnutzer
----------------------------------

Es ist wichtig, **Ihre Zielgruppe zu berücksichtigen: Kleinst- und Kleinunternehmen (Arbeitgeber und Personal), und der Aufbau** des Gefärhdunsbeurteilung-Tools sollte für die täglichen Aktivitäten der Unternehmen so relevant wie möglich sein; der Endnutzer denkt und handelt hinsichtlich seiner eigenen Geschäftsprozesse.

Oft weicht die Denkweise des Experten von der Praxis des Endnutzers ab. Letzterer denkt hinsichtlich seiner eigenen Arbeitsprozesse und benutzt seine eigene Sprache. Einige Beispiele:

  * der Experte denkt an die physische Arbeitsbelastung; *der Endnutzer an die physische Arbeit*

  * der Experte denkt an die thermische Umgebung; *der Endnutzer an die Arbeit bei Hitze/Kälte*

  * der Experte denkt an Sicherheit und entwirft ein Modul, das alles in diesem Bereich beinhaltet; *der Endnutzer denkt z.B. an die mit dem Öffnen und Schließen eines Ladens verbundenen Aspekte oder an den Umgang mit aggressiven Kunden.*

1.2 Einfacher Sprachgebrauch
----------------------------

**Wird der inhaltliche Aufbau des Risikobewertungs-Tools gemäß der Denk- und Handlungsweise des durchschnittlichen Endnutzers** strukturiert, so wird der Inhalt leicht verständlich und die Erstellung eines Aktionsplans zur Lösung der Risiken mit durchführbaren Maßnahmen erleichtert.

Ein anderer entscheidender Aspekt ist die verwendete Terminologie. Die **Sprache** sollte leicht verständlich sein und ohne Interpretationsspielraum sein. Sie sollte Begriffe enthalten, die den Unternehmen vertraut und geläufig sind.

Durch kurze Sätze (möglichst nicht länger als zehn Wörter) und eine für Laien leicht verständliche klare Alltagssprache wird einer Abneigung seitens des Endnutzers vorgebeugt. So kann er eine Bewertung durchführen und das OiRA-Tool ordnungsgemäß anwenden.

Zu Beginn haben Sie die Möglichkeit, einen kurzen Einführungstext zu schreiben, um eine positive **und motivierende Botschaft** bezüglich folgender Punkte zu vermitteln:

  * die **Wichtigkeit** der Gefährdungsbeurteilung

  * die Tatsache, dass Gefährdungsbeurteilung **nicht zwangsläufig kompliziert** ist (der Gedanke dahinter ist, dazu beizutragen, die Scheu vor der Gefährdungsbeurteilung zu überwinden)

  * die Tatsache, dass das Tool speziell dazu entwickelt wurde, um **den Bedürfnissen der Unternehmen Ihrer Branche gerecht zu werden**


Der Text sollte nicht zu lang sein, da der Endnutzer ansonsten die Motivation verliert, das Tool zu verwenden.

2. Team
=======

Obwohl es wichtig ist, das Projektteam von der Größe her überschaubar zu halten, sollte es vorzugsweise aus folgenden Mitgliedern bestehen:

  * Vertreter des (der) Unternehmerverbands(verbände)

  * Vertreter der Gewerkschaft(en)

  * der OiRA Entwickler

  * ein Experte für Arbeitsschutz (mit Branchenkenntnissen und Bezug zur Branche)

  * End-Nutzer (z.B. Leitung oder Personal der Unternehmen, Gewerkschaftsvertreter etc.)


3. Aufbau
=========

3.1 Hierarchisch aufgebauter Inhalt
-----------------------------------

Bevor Sie mit der Entwicklung eines OiRA-Tools beginnen, sollten Sie die Anzahl der Themen, die Sie ansprechen möchten, bedenken. Eine gute Strukturierung des Aufbaus wird sich später auszahlen, also sollten die Themen in einer für den Endnutzer relevanten Weise gegliedert werden.


Das System bietet die Möglichkeit, Themen, Unterthemen und Risikotypen in gemeinsamen Gruppen zu ordnen. Der Hauptzweck dieser Gruppierung ist, dem Endnutzer die Anwendung des Gefährungsbeurteilungs-Tools zu erleichtern/verständlicher zu machen. Ihr Gefährungsbeurteilungs-Tool wird daher aus folgenden Teilen bestehen:


.. image:: ../images/creation/module.png
  :align: left
  :height: 32 px

**MODULE** = Themen  (Orte, Aktivitäten,...)

  *Beispiel*:
    Modul 1: *Haare waschen*  (Friseurbranche)

  .. image:: ../images/creation/submodule.png
    :align: left
    :height: 32 px

  **UNTER-MODULE** (nicht zwingend erforderlich) = Unterthemen

    *Beispiel*:
      Untermodul 1: *Körperhaltung bei der Arbeit*

      Untermodul 2: *Kontakt mit Wasser und Kosmetikprodukten*

    .. image:: ../images/creation/risk.png
      :align: left
      :height: 32 px

    **GEFÄHRDUNGEN** = Angaben zu einer ordnungsgemäßen Situation

      *Beispiel*:
        *1.1 Das Kopfwaschbecken ist verstellbar*

        *2.1 Angemessene Schutzausrüstung, wie Einweghandschuhe, wurde angeschafft*

      .. image:: ../images/creation/solution.png
        :align: left
        :height: 32 px

      **LÖSUNGEN** = vom Experten vorgeschlagene vorbeugende Maßnahmen zur Lösung des Problems

        *Beispiel*:
          *1.1 Regelmäßige Ruhepausen bei körperlicher Arbeit*

          *2.1 Verwendung puderfreier Produkte*


Das System bietet auch folgende Möglichkeiten an:

  * das Überspringen eines/eines ganzen Satzes von Modulen, falls der Inhalt für die Aktivitäten des Unternehmens nicht zutrifft

  * die Wiederholung einiger Module, falls die Unternehmen mehrere Standorte haben

3.2 Die Angabe der Gefährdung als positive Aussage
--------------------------------------------------

Wenn Sie sich für den Hauptaufbau des Gefährungsbeurteilungs-Tools entschieden haben, können Sie mit der Ermittlung und dem Erklären der verschiedenen Risiken beginnen.

Das System arbeitet mit **positiven Aussagen**; es gibt an, **ob eine Situation ‘ordnungsgemäß’ (zu erreichendes Ziel) oder ‘nicht ordnungsgemäß’ ist**

.. note::

   Beispiel: Gute Beleuchtung ist vorhanden.

Der Endnutzer antwortet mit einem klaren ‘Ja’ oder ‘Nein’. Antwortet der Endnutzer mit Nein (= die Situation ist nicht ordnungsgemäß), wird das Problem automatisch in den Aktionsplan übernommen, und der Endnutzer muss eine Maßnahme vorschlagen, um die Gefährdung zu handhaben.

3.3 Die verschiedenen Gefährdungstypen
--------------------------------------

Sie können zwischen 3 Gefährdungstypen wählen:

  * **Prioritätsgefährdung**: bezieht sich auf eine Gefährdung, das laut Branche zu den hohen Risiken in der Branche zählt.

    .. note::

      Beispiel: Gerüstarbeiten in der Baubranche: das Gerüst ist auf einem festen Untergrund aufgestellt


  * **Gefährdung**: bezieht sich auf vorhandene Gefährdungen am Arbeitsplatz oder ist mit der auszuführenden Arbeit verbunden.

    .. note::

      Beispiel: Alle Bürostühle sind verstellbar

Um die oben genannten zwei Gefährdungstypen zu erkennen und zu bewerten, ist es oftmals erforderlich, den Arbeitsplatz zu untersuchen (Rundgang am Arbeitsplatz, um zu sehen, was Schäden herbeiführen könnte; Befragung des Personals, ...).

 * **Firmenpolitik**: bezieht sich auf Vereinbarungen, Abläufe und Entscheidung der Leitung bezüglich der Arbeitssicherheit.

   .. note::

     Beispiel: Produzenten werden regelmäßig zu alternativen sicheren Produkten befragt

Diese Angaben zur Firmenpolitik können vom Schreibtisch aus beantwortet werden (eine Untersuchung des Arbeitsplatzes ist nicht erforderlich).


3.4 Voreingestellte Bewertung der Gefährdung
--------------------------------------------

Für jeden “Gefährdungs”-Typ können Sie zwischen 2 Bewertungsmethoden wählen:

  * **Schätzung**: durch Wahl zwischen **hoch, mittel** oder **gering**.

  * **Berechnung**: durch getrennte Beurteilung von **Wahrscheinlichkeit, Häufigkeit** and **Schweregrad**. Das OiRA-Tool wird dann automatisch die Priorität berechnen.

Endnutzer müssen die folgenden Risiken in der "Bewertungs”-Stufe nicht beurteilen:

  * Prioritätsgefährdungen (durch Voreinstellung als “hohe Priorität” eingestuft und im Aktionsplan als “hoch” verzeichnet)

  * Firmenpolitik (dies ist streng genommen kein Risiko).


3.5 Lösungsvorschläge
---------------------

Die Branche ist generell gut über die Gefährdungen, die am wahrscheinlichsten zu Berufsunfällen und -krankheiten führen, informiert. Um dem Endnutzer bei bei der Handhabung dieser Gefährdungen zu helfen, können Sie die von der Branche/Experten vorgeschlagenen Lösungen mit einbeziehen. Bei der Erstellung des Aktionsplans haben die Endnutzer die Möglichkeit, Lösungen auszuwählen und diese entsprechend den Gegebenheiten in ihrem Unternehmen zu überarbeiten (den Text zu ändern).

.. note::

  Alle erforderlichen Dokumente sind auf der OiRA-Homepage erhältlich: http://www.oiraproject.eu/doc/
