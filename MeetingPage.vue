<template>
  <div>
    <button @click="openMeetingEditor()" v-show="!editorVisible">Dodaj nowe spotkanie</button>
    <new-meeting-form
      v-if="editorVisible"
      @added="addNewMeeting($event)">
    </new-meeting-form>
  
    <p v-if="meetings.length < 1">Nie masz zaplanowanych spotkań</p>
    
    <div v-if="meetings.length > 0">
      <h2>Zaplanowane zajęcia ({{meetings.length}})</h2>
      <meetings-list
        :meetings="meetings"
        :user="user"
        @subscribe="addParticipant($event)"
        @unsubscribe="removeParticipant($event)"
        @removed="removeMeeting($event)">
      </meetings-list>
    </div>
  </div>
</template>

<script>
  import NewMeetingForm from "./NewMeetingForm";
  import MeetingsList from "./MeetingsList";
  
  export default {
    components: {NewMeetingForm, MeetingsList},
    props: ['user'],
    data() {
      return {
        meetings: [],
        editorVisible: false,
      };
    },
    methods: {
      addNewMeeting(meeting) {
        this.meetings.push(meeting);
        this.editorVisible = false;
      },
      removeMeeting(meeting) {
        this.meetings = this.meetings.filter((event) => {
          return event !== meeting;
        });
      },
      openMeetingEditor() {
        this.editorVisible = true;
      },
      addParticipant(meeting) {
        meeting.participants.push(this.user);
      },
      removeParticipant(meeting) {
        meeting.participants = meeting.participants.filter((participant) => {
          return participant !== this.user;
        });
      }
    }
  }
</script>
