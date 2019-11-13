<template>
  <div class="page">
    <div class="container">
      <input type="text" placeholder="Søg borger" class="input-citizen"/>
      <div class="note-section">
        <div class="note-header">
          <h3 class="title">H7IP</h3>
          <button class="add-note">Opret ny notat</button>
        </div>
        <div class="note-list" v-for="(note, index) in notes" :key="index">
          <div class="note-item">
            <div class="user-info">
              <img :src="note.avatar" class="user-avatar" />
              <span class="user-name">{{note.name}}</span>
              <div class="vertical-line"></div>
            </div>
            <div class="note-content">
              <div class="main-note">
                <div class="note-date">
                  <span>{{note.daysago}} dage siden</span>
                </div>
                <div class="note-desc">
                  {{note.note}}
                </div>
              </div>
              <div class="note-comments">
                <div class="view-more" v-if="note.comments.length >= 2">Vi mere</div>
                <div class="comments-list" v-for="(comment, index) in note.comments" :key="index">
                  <div class="comment-item">
                    <div class="comment-avatar">
                      <img :src="comment.avatar" class="avatar-img" />
                    </div>
                    <div class="comment-content">
                      <div class="comment-header">
                        <span class="comment-user-name">{{comment.name}}</span>
                        <span class="comment-date">{{comment.daysago}} dage siden</span>
                      </div>
                      <div class="comment-desc">
                        {{comment.comment}}
                      </div>
                    </div>
                  </div>
                </div>
                <div class="add-comment">
                  <input type="text" class="comment-input" placeholder="Tilføj kommentar" />
                  <button class="add-comment-button">Tilføj</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Page",
  props: {
    notes: Array
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .page {
    background: #edecec;
    padding: 50px 0;

    .container {
      width: 70%;
      margin: 0 auto;
    }

    .input-citizen {
      width: 100%;
      height: 40px;
      border: 1px solid #cbcbcb;
      border-radius: 5px;
      text-indent: 20px;
      font-size: 18px;
      color: #aeaeae;
    }

    .note-section {
      margin-top: 30px;

      .note-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        border-bottom: 1px solid #a3a3a3;

        .title {
          font-size: 25px;
          color: #6a6a6a;
          margin: 10px 0;
        }

        .add-note {
          background: #84d024;
          color: #fff;
          font-size: 18px;
          padding: 0 25px;
          height: 40px;
          border-radius: 8px;
        }
      }

      .note-list {
        padding-left: 80px;

        .note-item {
          margin-top: 60px;
          display: flex;

          .user-info {
            width: 140px;
            padding-right: 60px;
            display: flex;
            flex-direction: column;
            align-items: center;

            .user-avatar {
              background: #c8c8c8;
              border-radius: 50%;
              width: 80px;
              margin-bottom: 10px;
              box-shadow: 0 5px 10px #b4b4b4;
            }

            .user-name {
              font-size: 16px;
              font-weight: 700;
              color: #3e3e3e;
              margin-bottom: 10px;
            }

            .vertical-line {
              width: 5px;
              background: #e4e4e4;
              height: 100%;
            }
          }

          .note-content {
            background: #fff;
            border-radius: 15px;
            box-shadow: 0 5px 10px #c8c8c8;

            .main-note {
              width: 90%;
              margin: 0 auto;
              padding: 20px 0 30px;
              border-bottom: 2px solid #e1e1e1;

              .note-date {
                display: flex;
                justify-content: flex-end;
                margin-bottom: 30px;
                font-size: 15px;
                color: #777;
              }

              .note-desc {
                font-size: 16px;
                color: #4a4a4a;
                text-align: left;
              }
            }

            .note-comments {
              .view-more {
                margin-top: 10px;
                height: 60px;
                background: #f7f7f7;
                cursor: pointer;
                display: flex;
                align-items: center;
                justify-content: center;
                font-size: 20px;
                color: #707070;
              }

              .comments-list {
                padding: 30px 120px 30px 40px;

                .comment-item {
                  display: flex;
                  align-items: center;

                  .comment-avatar {
                    width: 90px;
                    padding-right: 30px;

                    .avatar-img {
                      background: #c8c8c8;
                      border-radius: 50%;
                      width: 60px;
                      height: 60px;
                      box-shadow: 0 5px 10px #b4b4b4;
                    }
                  }

                  .comment-content {
                    width: 100%;

                    .comment-header {
                      display: flex;
                      justify-content: space-between;
                      margin-bottom: 5px;

                      .comment-user-name {
                        font-size: 16px;
                        color: #000;
                      }

                      .comment-date {
                        font-size: 16px;
                        font-style: italic;
                        color: #989898;
                      }
                    }

                    .comment-desc {
                      text-align: left;
                      font-size: 16px;
                      color: #5b5b5b;
                    }
                  }
                }
              }

              .add-comment {
                height: 40px;
                background: #e2e2e2;
                padding: 15px 20px;
                display: flex;

                .comment-input {
                  width: 80%;
                  margin-right: 20px;
                  text-indent: 20px;
                  font-size: 18px;
                  color: #949494;
                  border: none;
                  border-radius: 8px;
                }

                .add-comment-button {
                  flex: 1 1 auto;
                  background: #84d024;
                  border-radius: 8px;
                  font-size: 20px;
                  color: #fff;
                }
              }
            }
          }
        }
      }
    }
  }
</style>
