<template>
  <el-form
    ref="form"
    :model="form"
    label-width="100px"
    @submit.prevent="onSubmit"
    style="margin:20px;width:60%;min-width:1000px;"
  >
    <el-form-item label="名称">
      <div style="display:flex">
        <el-input v-model="form.name" style="width:160px"></el-input>&nbsp;
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="维修" name="type"></el-checkbox>
          <el-checkbox label="维修加急" name="type"></el-checkbox>
          <el-checkbox label="鉴定" name="type"></el-checkbox>
          <el-checkbox label="鉴定加急" name="type"></el-checkbox>
        </el-checkbox-group>&nbsp;&nbsp;&nbsp;
        <div>
          保修卡号
          <el-input v-model="form.number" style="width:100px"></el-input>&nbsp;
        </div>
        <div>
          购买日期
          <el-input v-model="form.buydata" style="width:100px"></el-input>&nbsp;
        </div>
      </div>
    </el-form-item>
    <div style="display:flex">
      <div>
        <div style="display:flex">
          <div>
            <el-form-item label="客户名称">
              <el-select v-model="form.guestname" placeholder="请选择活动区域" style="width:200px">
                <el-option label="区域一" value="shanghai"></el-option>
                <el-option label="区域二" value="beijing"></el-option>
              </el-select>
            </el-form-item>
            <el-form-item label="地址">
              <el-select v-model="form.guestaddess" placeholder="请选择活动区域" style="width:300px">
                <el-option label="区域一" value="shanghai"></el-option>
                <el-option label="区域二" value="beijing"></el-option>
              </el-select>
            </el-form-item>
          </div>
          <el-form-item>
            <el-button style="height:100px;">
              客户
              <br>维修存档
              <br>查询
            </el-button>
          </el-form-item>
        </div>
        <div style="display:flex">
          <el-form-item label="联系人">
            <el-select v-model="form.contacts" placeholder="请选择活动区域">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="邮政编码">
            <el-input v-model="form.postcode" style="width:220px"></el-input>
          </el-form-item>
        </div>
      </div>
      <el-form-item label="仪器故障描述">
        <el-input
          type="textarea"
          :rows="7"
          placeholder="请输入内容"
          v-model="form.marshertextarea"
          style="width:250px"
        ></el-input>
      </el-form-item>
    </div>
    <div style="display:flex">
      <el-form-item label="电话1">
        <el-input v-model="form.phone1" style="width:220px"></el-input>
      </el-form-item>
      <el-form-item label="电话2">
        <el-input v-model="form.phone2" style="width:220px"></el-input>
      </el-form-item>
      <el-form-item label="指定鉴定单位">
        <el-input v-model="form.identification" style="width:220px"></el-input>
      </el-form-item>
    </div>
    <div style="display:flex">
      <div>
        <div style="display:flex">
          <el-form-item label="仪器名称">
            <el-select v-model="form.machinename" placeholder="请选择活动区域">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="仪器型号">
            <el-select v-model="form.machinecode" placeholder="请选择活动区域">
              <el-option label="区域一" value="shanghai"></el-option>
              <el-option label="区域二" value="beijing"></el-option>
            </el-select>
          </el-form-item>
        </div>
        <div style="display:flex">
          <el-form-item label="机身号码">
            <el-input v-model="form.machineno" style="width:370px"></el-input>
          </el-form-item>
          <el-form-item label="仪器数量">
            <el-input v-model="form.machinenumber" style="width:60px"></el-input>
          </el-form-item>
        </div>
      </div>
      <el-form-item label="送机人(客户签名)">
        <el-input
          type="textarea"
          :rows="4"
          placeholder="请输入内容"
          v-model="form.machinegiving"
          style="width:250px"
        ></el-input>
      </el-form-item>
    </div>
    <div style="display:flex">
      <div>
        <div style="display:flex">
          <div>
            <div style="display:flex">
              <div>
                <el-form-item label="随机附件1">
                  <el-select v-model="form.radom1" placeholder="请选择活动区域" style="width:100px">
                    <el-option label="区域一" value="shanghai"></el-option>
                    <el-option label="区域二" value="beijing"></el-option>
                  </el-select>
                </el-form-item>
                <el-form-item label="随机附件2">
                  <el-select v-model="form.radom2" placeholder="请选择活动区域" style="width:100px">
                    <el-option label="区域一" value="shanghai"></el-option>
                    <el-option label="区域二" value="beijing"></el-option>
                  </el-select>
                </el-form-item>
                <el-form-item label="随机附件3">
                  <el-select v-model="form.radom3" placeholder="请选择活动区域" style="width:100px">
                    <el-option label="区域一" value="shanghai"></el-option>
                    <el-option label="区域二" value="beijing"></el-option>
                  </el-select>
                </el-form-item>
                <el-form-item label="随机附件4">
                  <el-select v-model="form.radom4" placeholder="请选择活动区域" style="width:100px">
                    <el-option label="区域一" value="shanghai"></el-option>
                    <el-option label="区域二" value="beijing"></el-option>
                  </el-select>
                </el-form-item>
                <el-form-item label="随机附件5">
                  <el-select v-model="form.radom5" placeholder="请选择活动区域" style="width:100px">
                    <el-option label="区域一" value="shanghai"></el-option>
                    <el-option label="区域二" value="beijing"></el-option>
                  </el-select>
                </el-form-item>
                <el-form-item label="随机附件6">
                  <el-select v-model="form.radom6" placeholder="请选择活动区域" style="width:100px">
                    <el-option label="区域一" value="shanghai"></el-option>
                    <el-option label="区域二" value="beijing"></el-option>
                  </el-select>
                </el-form-item>
              </div>
              <div>
                <el-form-item label="附件1数量">
                  <el-input v-model="form.radomnum1" style="width:100px"></el-input>
                </el-form-item>
                <el-form-item label="附件2数量">
                  <el-input v-model="form.radomnum2" style="width:100px"></el-input>
                </el-form-item>
                <el-form-item label="附件3数量">
                  <el-input v-model="form.radomnum3" style="width:100px"></el-input>
                </el-form-item>
                <el-form-item label="附件4数量">
                  <el-input v-model="form.radomnum4" style="width:100px"></el-input>
                </el-form-item>
                <el-form-item label="附件5数量">
                  <el-input v-model="form.radomnum5" style="width:100px"></el-input>
                </el-form-item>
                <el-form-item label="附件6数量">
                  <el-input v-model="form.radomnum6" style="width:100px"></el-input>
                </el-form-item>
              </div>
            </div>
          </div>
          <div>
            <div style="margin-left: 10px;">其他附件</div>
            <div style="margin-left: 10px;">
              <el-input
                type="textarea"
                :rows="14"
                placeholder="请输入内容"
                v-model="form.otherradom"
                style="width:230px"
              ></el-input>
            </div>
          </div>
        </div>
      </div>
      <div>
        <div style="display:flex">
          <el-form-item label="接收经办人">
            <el-input v-model="form.charge" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="接收日期">
            <el-date-picker
              v-model="form.chargedata"
              type="date"
              placeholder="选择日期"
              style="width:120px"
            ></el-date-picker>
          </el-form-item>
        </div>
        <el-form-item label="取机人(客户签名)">
          <el-input
            type="textarea"
            :rows="3"
            placeholder="请输入内容"
            v-model="form.takeoutmachine"
            style="width:100px"
          ></el-input>
        </el-form-item>
        <div style="display:flex">
          <el-form-item label="取机经办人">
            <el-input v-model="form.takeoutmachineworker" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="取发日期">
            <el-date-picker
              v-model="form.takeoutmachinedata"
              type="date"
              placeholder="选择日期"
              style="width:120px"
            ></el-date-picker>
          </el-form-item>
        </div>
        <div style="display:flex">
          <el-form-item label="收款人">
            <el-input v-model="form.payee" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="收款日期">
            <el-date-picker
              v-model="form.payeedata"
              type="date"
              placeholder="选择日期"
              style="width:120px"
            ></el-date-picker>
          </el-form-item>
        </div>
        <el-form-item label="派单人">
          <el-input v-model="form.leaflet" style="width:100px"></el-input>
        </el-form-item>
      </div>
    </div>
    <div style="display:flex">
      <el-button>查找记录</el-button>
      <el-button>添加记录</el-button>
      <el-button>复制到新纪录</el-button>
      <el-button>保存记录</el-button>
      <el-button>打印客户取机单</el-button>
      <el-button>打印财务结算单</el-button>
      <el-button>打印送修送检发货单</el-button>
      <el-button>打印惠普派工单</el-button>
      <el-button>提成查询</el-button>
      <el-button>导出提成查询表</el-button>
    </div>
    <div style="display:flex">
      <div>
        <el-form-item label="分公司">
          <el-select v-model="form.branch" placeholder="请选择活动区域" style="width:100px">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="业务归属">
          <el-select v-model="form.business" placeholder="请选择活动区域" style="width:100px">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="属性">
          <el-select v-model="form.attribute" placeholder="请选择活动区域" style="width:100px">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="仪器分类">
          <el-select v-model="form.classification" placeholder="请选择活动区域" style="width:100px">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="维修分类">
          <el-select v-model="form.repair" placeholder="请选择活动区域" style="width:100px">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
      </div>
      <div>
        <el-form-item label="定价日期">
          <el-date-picker v-model="form.price" type="date" placeholder="选择日期" style="width:120px"></el-date-picker>
        </el-form-item>
        <el-form-item label="报价待复">
          <el-date-picker v-model="form.offer" type="date" placeholder="选择日期" style="width:120px"></el-date-picker>
        </el-form-item>
        <el-form-item label="同意日期">
          <el-date-picker v-model="form.agree" type="date" placeholder="选择日期" style="width:120px"></el-date-picker>
        </el-form-item>
        <el-form-item label="派单日期">
          <el-date-picker
            v-model="form.senddata"
            type="date"
            placeholder="选择日期"
            style="width:120px"
          ></el-date-picker>
        </el-form-item>
        <el-form-item label="完成日期">
          <el-date-picker
            v-model="form.complatedata"
            type="date"
            placeholder="选择日期"
            style="width:120px"
          ></el-date-picker>
        </el-form-item>
      </div>
      <div>
        <div style="display:flex">
          <el-form-item label="维修员">
            <el-input v-model="form.fixmen" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="发广分日期">
            <el-date-picker
              v-model="form.guanzhou"
              type="date"
              placeholder="选择日期"
              style="width:120px"
            ></el-date-picker>
          </el-form-item>
          <el-form-item label="广分维修单号">
            <el-input v-model="form.guanzhounum" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="广分返回日期">
            <el-date-picker
              v-model="form.guanzhougivedata"
              type="date"
              placeholder="选择日期"
              style="width:120px"
            ></el-date-picker>
          </el-form-item>
        </div>
        <div style="display:flex">
          <el-form-item label="价格">
            <el-input v-model="form.pricetwice" style="width:100px"></el-input>
          </el-form-item>
          <div style="margin-left:10px">
            <el-checkbox-group v-model="form.appraisal">
              <el-checkbox label="已收鉴定费" name="type"></el-checkbox>
            </el-checkbox-group>
          </div>
          <el-form-item label="已收金额" v-model="form.amountreceived">
            <el-input v-model="form.phone2" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="核实人" v-model="form.verifying">
            <el-input v-model="form.phone2" style="width:100px"></el-input>
          </el-form-item>
        </div>
        <div style="display:flex">
          <el-form-item label="价格2">
            <el-input v-model="form.pricetwice2" style="width:100px"></el-input>
          </el-form-item>
          <div style="margin-left:10px">
            <el-checkbox-group v-model="form.check">
              <el-checkbox label="支票或转账到公司" name="type"></el-checkbox>
            </el-checkbox-group>
          </div>
          <div style="margin-left:10px">
            <el-checkbox-group v-model="form.cash">
              <el-checkbox label="现金结算" name="type"></el-checkbox>
            </el-checkbox-group>
          </div>
          <div style="margin-left:10px">
            <el-checkbox-group v-model="form.identification11">
              <el-checkbox label="款转鉴定所" name="type"></el-checkbox>
            </el-checkbox-group>
          </div>
        </div>
        <el-form-item label="鉴定费">
          <el-input v-model="form.appraisalfee" style="width:100px"></el-input>
        </el-form-item>
        <div style="display:flex">
          <el-form-item label="上门服务费">
            <el-input v-model="form.seruverfee" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="成本/厂家收费">
            <el-input v-model="form.costfee" style="width:100px"></el-input>
          </el-form-item>
          <el-form-item label="维修/鉴定费合计">
            <el-input v-model="form.fixfee" style="width:100px"></el-input>
          </el-form-item>
        </div>
      </div>
    </div>
    <div style="display:flex">
      <el-form-item label="修理项目1">
        <el-input v-model="form.fixproject1" style="width:200px"></el-input>
      </el-form-item>
      <el-form-item label="项目1修理/元件费">
        <el-input v-model="form.fixmachineelement1" style="width:200px"></el-input>
      </el-form-item>
      <el-form-item label="修理项目4">
        <el-input v-model="form.fixproject4" style="width:200px"></el-input>
      </el-form-item>
      <el-form-item label="项目4修理/元件费">
        <el-input v-model="form.fixmachineelement4" style="width:200px"></el-input>
      </el-form-item>
    </div>
    <div style="display:flex">
      <el-form-item label="修理项目2">
        <el-input v-model="form.fixproject2" style="width:200px"></el-input>
      </el-form-item>
      <el-form-item label="项目2修理/元件费">
        <el-input v-model="form.fixmachineelement2" style="width:200px"></el-input>
      </el-form-item>
      <el-form-item label="修理项目5">
        <el-input v-model="form.fixproject5" style="width:200px"></el-input>
      </el-form-item>
      <el-form-item label="项目5修理/元件费">
        <el-input v-model="form.fixmachineelement5" style="width:200px"></el-input>
      </el-form-item>
    </div>
    <div style="display:flex">
      <div>
        <div style="display:flex">
          <el-form-item label="修理项目3">
            <el-input v-model="form.fixproject3" style="width:200px"></el-input>
          </el-form-item>
          <el-form-item label="项目3修理/元件费">
            <el-input v-model="form.fixmachineelement3" style="width:200px"></el-input>
          </el-form-item>
        </div>
        <div style="display:flex">
          <el-form-item label="外送厂家名称">
            <el-input v-model="form.deliverymanufacturer" style="width:200px"></el-input>
          </el-form-item>
          <el-form-item label="外送日期">
            <el-input v-model="form.outwarddata" style="width:200px"></el-input>
          </el-form-item>
          <el-form-item label="返回日期">
            <el-input v-model="form.givingdata" style="width:200px"></el-input>
          </el-form-item>
        </div>
      </div>
      <el-form-item label="其他修理项目">
        <el-input
          type="textarea"
          :rows="4"
          placeholder="请输入内容"
          v-model="form.otherfixproject"
          style="width:130px"
        ></el-input>
      </el-form-item>
    </div>
    <el-form-item label="备注">
      <el-input
        type="textarea"
        :rows="4"
        placeholder="请输入内容"
        v-model="form.remarks"
        style="width:600px"
      ></el-input>
    </el-form-item>
  </el-form>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        type: [],
        number: "",
        buydata: "",
        guestname: "",
        guestaddess: "",
        contacts: "",
        postcode: "",
        marshertextarea: "",
        phone1: "",
        phone2: "",
        Identification: "",
        machinename: "",
        machinecode: "",
        machineno: "",
        machinenumber: "",
        machinegiving: "",
        radom1: "",
        radom2: "",
        radom3: "",
        radom4: "",
        radom5: "",
        radom6: "",
        radomnum1: "",
        radomnum2: "",
        radomnum3: "",
        radomnum4: "",
        radomnum5: "",
        radomnum6: "",
        otherradom: "",
        charge: "",
        chargedata: "",
        takeoutmachine: "",
        takeoutmachineworker: "",
        takeoutmachinedata: "",
        payee: "",
        payeedata: "",
        leaflet: "",
        branch: "",
        business: "",
        attribute: "",
        classification: "",
        repair: "",
        price: "",
        offer: "",
        agree: "",
        senddata: "",
        complatedata: "",
        fixmen: "",
        guanzhou: "",
        guanzhounum: "",
        guanzhougivedata: "",
        pricetwice: "",
        appraisal: [],
        amountreceived: "",
        verifying: "",
        pricetwice2: "",
        check: [],
        cash: [],
        identification11: [],
        appraisalfee: "",
        seruverfee: "",
        costfee: "",
        fixfee: "",
        fixproject1: "",
        fixmachineelement1: "",
        fixproject4: "",
        fixmachineelement4: "",
        fixproject2: "",
        fixmachineelement2: "",
        fixproject5: "",
        fixmachineelement5: "",
        fixproject3: "",
        fixmachineelement3: "",
        deliverymanufacturer: "",
        outwarddata: "",
        givingdata: "",
        otherfixproject: "",
        remarks: ""
      }
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    }
  }
};
</script>