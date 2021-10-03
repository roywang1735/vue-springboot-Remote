<template><!--component/template-->
    <div id="app" align='center' style='text-align:center;width:600px'>
      <vue-simple-menu :raw-menu-data="rawMenuData"></vue-simple-menu>
        <div class="site-info">
            <h3>會員管理系統</h3>
        </div>
        <div align='center'>
            <table>
              <tr>
                <td style='width:150px;vertical-align:top;background-color:lightblue;height:400px'>
                  <div style='background-color:yellow;font-weight:bold;text-align:center'><router-link  to="/">帳號</router-link></div>
                </td>
                <td>&nbsp;&nbsp;&nbsp;&nbsp;</td>
                <td style='vertical-align:top;width:400px'>
                    &#10074;<router-link  to="/">帳號列表</router-link>&nbsp;
                    &#10074;<router-link  to="/add">帳號新增</router-link>&nbsp;
                    &#10074;<router-link  to="/search">帳號搜尋</router-link>&nbsp;
                    <router-view/>
                </td>
              </tr>
            </table>
        </div>           
    </div>

    
</template>

<script>
export default {
  name: "app"
};
</script>







<style>
.site-info {
  color: blue;
  margin-bottom: 20px;
  background-color:orange;
}

.btn-primary {
  margin-right: 5px;
}

.container-fluid {
  text-align: center;
}
</style>
