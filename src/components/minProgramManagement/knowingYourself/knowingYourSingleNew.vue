<template>
  <div class="listpagewrap">
    <!--面包屑-->
    <breadcrumb :breadcrumb="breadcrumb"></breadcrumb>
    <index-common
      :formdata="formData"
      :tabledata="tableDate"
      :submitLoading="submitLoading"
      @addRow="addRow"
      @delrow="delrow"
      @submit="submit"
    ></index-common>
  </div>
</template>

<script>
import IndexCommon from "@/components/common/action/contactIndexCommon";
import Breadcrumb from "@/components/common/action/Breadcrumb.vue";
export default {
  components: { IndexCommon, Breadcrumb },
  data() {
    return {
    	submitLoading:false,
      submitUrl: "test/saveSingleTopic",
      breadcrumb: {
        search: false,
        searching: ""
      },
      tableDate: {
        tabletype: {
          type: "topic",
          distinction: "single"
        },
        problem: [
          {
            label: "问题:",
            prop: "topic",
            placeholder: "请填写问题"
          }
        ],
        hearder: [
          {
            prop: "option",
            label: "选项",
            width: "80"
          },
          {
            prop: "result",
            label: "答案及测试结果"
          },
          {
            prop: "rank",
            label: "危险测评",
            width: "124"
          }
        ],
        body: [
          {
            module: {
              result: "",
              rank: "",
              option: ""
            },
            result: [
              {
                text: "",
                placeholder: "请输入答案",
                height: "0.3rem",
                prop: "option",
                disabled: false
              },
              {
                text: "",
                placeholder: "请输入测试结果",
                height: "0.8rem",
                prop: "result",
                disabled: false
              }
            ],
            rank: [
              {
                text: "优秀",
                value: 1,
                prop: "rank",
                textcolor: "#20a235",
                class: "fine"
              },
              {
                text: "良好",
                value: 2,
                prop: "rank",
                textcolor: "#2871df",
                class: "good"
              },
              {
                text: "危险",
                value: 3,
                textcolor: "#df2828",
                class: "danger",
                prop: "rank"
              }
            ]
          },{
            module: {
              result: "",
              rank: "",
              option: ""
            },
            result: [
              {
                text: "",
                placeholder: "请输入答案",
                height: "0.3rem",
                prop: "option",
                disabled: false
              },
              {
                text: "",
                placeholder: "请输入测试结果",
                height: "0.8rem",
                prop: "result",
                disabled: false
              }
            ],
            rank: [
              {
                text: "优秀",
                value: 1,
                prop: "rank",
                textcolor: "#20a235",
                class: "fine"
              },
              {
                text: "良好",
                value: 2,
                prop: "rank",
                textcolor: "#2871df",
                class: "good"
              },
              {
                text: "危险",
                value: 3,
                textcolor: "#df2828",
                class: "danger",
                prop: "rank"
              }
            ]
          },{
            module: {
              result: "",
              rank: "",
              option: ""
            },
            result: [
              {
                text: "",
                placeholder: "请输入答案",
                height: "0.3rem",
                prop: "option",
                disabled: false
              },
              {
                text: "",
                placeholder: "请输入测试结果",
                height: "0.8rem",
                prop: "result",
                disabled: false
              }
            ],
            rank: [
              {
                text: "优秀",
                value: 1,
                prop: "rank",
                textcolor: "#20a235",
                class: "fine"
              },
              {
                text: "良好",
                value: 2,
                prop: "rank",
                textcolor: "#2871df",
                class: "good"
              },
              {
                text: "危险",
                value: 3,
                textcolor: "#df2828",
                class: "danger",
                prop: "rank"
              }
            ]
          },{
            module: {
              result: "",
              rank: "",
              option: ""
            },
            result: [
              {
                text: "",
                placeholder: "请输入答案",
                height: "0.3rem",
                prop: "option",
                disabled: false
              },
              {
                text: "",
                placeholder: "请输入测试结果",
                height: "0.8rem",
                prop: "result",
                disabled: false
              }
            ],
            rank: [
              {
                text: "优秀",
                value: 1,
                prop: "rank",
                textcolor: "#20a235",
                class: "fine"
              },
              {
                text: "良好",
                value: 2,
                prop: "rank",
                textcolor: "#2871df",
                class: "good"
              },
              {
                text: "危险",
                value: 3,
                textcolor: "#df2828",
                class: "danger",
                prop: "rank"
              }
            ]
          }
        ]
      },
      formData: {
        title: "新建单题测试",
        addrowTitle: "增加选项",
        model: {
          title: "",
          form: "单题测试",
          type: "",
          articleSource: "",
          summarize: "",
          image: "",
          topic: ""
          //
        },
        data: [
          {
            label: "标题名称:",
            labelWidth: "",
            prop: "title",
            span: 40,
            type: "",
            placeholder: "请填写标题名称"
          },
          {
            label: "测试题形式:",
            labelWidth: "",
            class: "mini",
            prop: "form",
            type: "text",
            disabled: true
            // data: [
            //   {
            //     index: 1,
            //     label: "学院机构",
            //     value: "111"
            //   }
            // ]
          },
          {
            label: "测试类别:",
            labelWidth: "",
            class: "mini",
            prop: "type",
            type: "select",
            data: [
              // 1性格2情感3健康4人际
              {
                index: 1,
                label: "性格",
                value: "1"
              },
              {
                index: 1,
                label: "情感",
                value: 2
              },
              {
                index: 1,
                label: "健康",
                value: 3
              },
              {
                index: 1,
                label: "人际",
                value: 4
              }
            ]
          },
          {
            label: "来源:",
            labelWidth: "",
            prop: "articleSource",
            class: "mini",
            span: 20,
            type: "",
            placeholder: "请填写来源"
          },
          {
            label: "摘要:",
            labelWidth: "",
            prop: "summarize",
            type: "",
            placeholder: "请填写摘要你"
          },
          {
            label: "封面照片:",
            labelWidth: "",
            prop: "image",
            type: "photo",
            height: "1.1rem"
          }
        ]
      }
    };
  },
  methods: {
    submit(form) {
    	if(!this.$_ault_alert('test:saveSingleTopic')){
	  			return
	  	}
      let valuenum = 0,
        objlength = 0;
      for (var i in this.tableDate.body[this.tableDate.body.length - 1]
        .module) {
        objlength += 1;
        if (
          this.tableDate.body[this.tableDate.body.length - 1].module[i] == ""
        ) {
          this.$notify({
            title: "警告",
            message: "请填写完整题目内容",
            type: "warning"
          });
          return;
        } else if (this.tableDate.body.length <= 1) {
          this.$notify({
            title: "警告",
            message: "请上传2个以上选项",
            type: "warning"
          });
          return;
        } else {
          valuenum += 1;
        }
      }
      if (objlength == valuenum) {
        let forms = form.model,
          singleOption = [];
        this.tableDate.body.forEach((v, i) => {
          let option = {};
          option["options"] = v.module.option;
          option["result"] = v.module.result;
          option["rank"] = v.module.rank;
          singleOption.push(option);
        });
      	this.submitLoading=true
        this.$http({
          method: "post",
          url: this.apiRoot + this.submitUrl,
          transformRequest: [
            function(data) {
              // Do whatever you want to transform the data
              let ret = "";
              for (let it in data) {
                ret +=
                  encodeURIComponent(it) +
                  "=" +
                  encodeURIComponent(data[it]) +
                  "&";
              }
              return ret;
            }
          ],
          headers: { "Content-Type": "application/x-www-form-urlencoded" },
          data: {
            test: JSON.stringify({
              title: forms.title,
              form: forms.form,
              type: forms.type,
              articleSource: forms.articleSource,
              summarize: forms.summarize,
              image: forms.image
            }),
            topic: JSON.stringify({ topic: forms.topic }),
            singleOptions: JSON.stringify(singleOption)
          }
        })
          .then(
            function(response) {
              if(response.data.success){
				     		this.$notify({
				          	title: '操作成功',
				          	message: '测试题新建成功！！！',
				          	type: 'success'
				        });
			        	this.$router.go(-1)
				     	}else{
				     		this.$notify.error({
				          	title: '操作失败',
				          	message: '测试题新建失败！！！',
				        });
				     	}
            }.bind(this)
          )
          .catch(
            function(error) {
              console.log(error);
            }.bind(this)
          );
      }
    },
    addRow() {
      if (this.tableDate.body.length == 4) {
        this.$notify({
          title: "警告",
          message: "已到最大选择项",
          type: "warning"
        });
      } else {
        let params = {
          module: {
            result: "",
            rank: "",
            option: ""
          },
          result: [
            {
              text: "",
              placeholder: "请输入答案",
              height: "0.3rem",
              prop: "option",
              disabled: false
            },
            {
              text: "",
              placeholder: "请输入测试结果",
              height: "0.8rem",
              prop: "result",
              disabled: false
            }
          ],
          rank: [
            {
              text: "优秀",
              value: 1,
              prop: "rank",
              textcolor: "#20a235",
              class: "fine"
            },
            {
              text: "良好",
              value: 2,
              prop: "rank",
              textcolor: "#2871df",
              class: "good"
            },
            {
              text: "危险",
              value: 3,
              textcolor: "#df2828",
              class: "danger",
              prop: "rank"
            }
          ]
        };
        let valuenum = 0,
          objlength = 0;
        for (var i in this.tableDate.body[this.tableDate.body.length - 1]
          .module) {
          objlength += 1;
          if (
            this.tableDate.body[this.tableDate.body.length - 1].module[i] == ""
          ) {
            this.$notify({
              title: "警告",
              message: "请填写完整题目内容",
              type: "warning"
            });
            return;
          } else {
            valuenum += 1;
          }
        }
        if (objlength == valuenum) {
          this.tableDate.body[
            this.tableDate.body.length - 1
          ].result[0].disabled = true;
          this.tableDate.body[
            this.tableDate.body.length - 1
          ].result[1].disabled = true;
//        console.log(this.tableDate.body[this.tableDate.body.length - 1]);
          this.tableDate.body.push(params);
        }
      }
    },
    delrow(e) {
      this.tableDate.body.splice(e, 1);
      this.tableDate.body[
        this.tableDate.body.length - 1
      ].result[0].disabled = false;
      this.tableDate.body[
        this.tableDate.body.length - 1
      ].result[1].disabled = false;
    }
  }
};
</script>

<style>
</style>
