<template>
 <ModalBox @close="$emit('close')"
 left="5"
           right="5"
           top="4"
           bottom="5"
           borderRadius="1.4"
 >

     <div class="impressumText">
       <p>
         Hold Hands hat erstmalig im April 2016 in den Räumen des Kulturvereins Pracht e.V. Leipzig stattgefunden und wurde durch die Künstlerin Lissy Willberg initiiert. Es war eine Veranstaltung, die queere und weibliche* Positionen in Performance-, Poetry-, Video- und Installationskunst zusammenbrachte und ausstellte. Vier Studierende der Hochschule für Grafik und Buchkunst, sowie internationale Künstler:innen haben sich mit Beiträgen am Programm beteiligt. Die Idee von Hold Hands als Plattform für den Austausch und die Präsentation dieser Positionen sollte im Frühjahr 2020 fortgesetzt werden; eine öffentliche Veranstaltung konnte jedoch aufgrund der globalen Pandemie nicht stattfinden. Infolgedessen entstand der Gedanke das Projekt im Jahr 2021 um ein Online-Residenzprogramm zu erweitern.

       </p>
       <p>
         Viele Künstler:innen sehen sich aktuell vor der Herausforderung digitale Räume zu bespielen. Die Initiator:innen von Hold Hands Residenz sehen ein Defizit in der theoretischen und praktischen Beschäftigung mit dieser Thematik und möchten durch das Residenzprogramm einen digitalen Experimentierraum schaffen, der einen kollektiven Diskurs anregt und die Hinterfragung konventioneller Methodik fördert.

       </p>
       <p>
         Das Projekt Hold Hands Residenz wird umgesetzt von:
         <br>

         Hjördis Lyn Behncken (Social Media und Öffentlichkeitsarbeit)<br>
         Anne Dietzsch (gestalterisches Konzept und Typografie)<br>
         Jonathan Schneider (Programmierung)<br>
         Lissy Willberg (inhaltliches Konzept, Projektleitung und Videoproduktion)<br>

         und gefördert durch das Kulturamt Leipzig und das Support-Büro der HGB Leipzig.

       </p>

       <address>
         Kontakt:
         <br>
         mail ( at ) hold-hands.net
         <br>
         Hold Hands Residenz   <br>
         c/o Lissy Willberg   <br>
         Herbartstr. 75   <br>
         04318 Leipzig
         <br><br><br>
       </address>
     </div>

   </ModalBox>
</template>

<script>
import ModalBox from "@/components/ModalBox";
export default {
  name: "ImpressumModal",
  components: {
    ModalBox
  }
}
</script>

<style scoped>

.impressumText {

  top: 0;
  height: 100%;
  overflow: auto;
padding-left: 2vw;
  background: #b2b2b2;
}


</style>
