<template>
  <section class="content">
      <content-header
              title="Calendar"
              description="Calendar">
      </content-header>

      <!-- Main content -->
      <div class="content">
          <div class="container-fluid">
              <div class="row">
                  <div class="col-md-3">
                      <div class="card">
                          <div class="card-header">
                              <h4 class="card-title">Draggable Events</h4>
                          </div>
                          <div class="card-body">
                              <!-- the events -->
                              <div id="external-events">
                                  <div class="external-event bg-success">Lunch</div>
                                  <div class="external-event bg-warning">Go home</div>
                                  <div class="external-event bg-info">Do homework</div>
                                  <div class="external-event bg-primary">Work on UI design</div>
                                  <div class="external-event bg-danger">Sleep tight</div>
                                  <div class="checkbox">
                                      <label for="drop-remove">
                                          <input type="checkbox" id="drop-remove">
                                          remove after drop
                                      </label>
                                  </div>
                              </div>
                          </div>
                          <!-- /.card-body -->
                      </div>
                      <!-- /.card -->
                      <div class="card">
                          <div class="card-header">
                              <h3 class="card-title">Create Event</h3>
                          </div>
                          <div class="card-body">
                              <div class="btn-group" style="width: 100%; margin-bottom: 10px;">
                                  <!--<button type="button" id="color-chooser-btn" class="btn btn-info btn-block dropdown-toggle" data-toggle="dropdown">Color <span class="caret"></span></button>-->
                                  <ul class="fc-color-picker" id="color-chooser">
                                      <li><a class="text-primary" href="#"><i class="fas fa-square"></i></a></li>
                                      <li><a class="text-warning" href="#"><i class="fas fa-square"></i></a></li>
                                      <li><a class="text-success" href="#"><i class="fas fa-square"></i></a></li>
                                      <li><a class="text-danger" href="#"><i class="fas fa-square"></i></a></li>
                                      <li><a class="text-muted" href="#"><i class="fas fa-square"></i></a></li>
                                  </ul>
                              </div>
                              <!-- /btn-group -->
                              <div class="input-group">
                                  <input id="new-event" type="text" class="form-control" placeholder="Event Title">

                                  <div class="input-group-append">
                                      <button id="add-new-event" type="button" class="btn btn-primary btn-flat">Add</button>
                                  </div>
                                  <!-- /btn-group -->
                              </div>
                              <!-- /input-group -->
                          </div>
                      </div>
                  </div>
                  <!-- /.col -->
                  <div class="col-md-9">
                      <div class="card card-primary">
                          <div class="card-body p-0">
                              <!-- THE CALENDAR -->
                              <calendar/>
                          </div>
                          <!-- /.card-body -->
                      </div>
                      <!-- /.card -->
                  </div>
                  <!-- /.col -->
              </div>
              <!-- /.row -->
          </div><!-- /.container-fluid -->
      </div>
      <!-- /.content -->
  </section>
</template>

<script>
  import ContentHeader from '@/layout/components/Content/ContentHeader.vue'
  import Calendar from '@/components/jQuery/pages/calendar.vue'  // todo

  export default {
        name: "Calendar",
        components: { ContentHeader, Calendar },

  }
</script>

<style>

</style>