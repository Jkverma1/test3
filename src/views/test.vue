<script>
import JsonData from "../../user.json";
var status = false;
export default {
  data() {
    return {
      Dropdown: status,
      data: JsonData,
    };
  },
};
</script>

<template>
  <div class="customDropdown">
    <div @click="Dropdown = !Dropdown" class="dropdownHeader">
      <span>Form Menu</span>
      <i v-if="Dropdown" class="fa-solid fa-chevron-up drop-icon"> </i>
      <i v-else class="fa-solid fa-chevron-down drop-icon"> </i>
    </div>
    <div v-if="Dropdown" class="dropdownItems">
      <ul class="dropdownList">
        <li v-for="subitem in data.sidebar[4].subMenu">
          <button class="sub-btn sub-dropdown-btn">
            <span
              ><img :src="subitem.iconPath" alt="" /> {{ subitem.name }}</span
            >
            <i class="fa-solid fa-chevron-down drop-icon"></i>
          </button>

          <ul>
            <li>hello</li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</template>
<style>
.dropdownHeader {
  width: 230px;
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
  border-radius: 10px;
  background-color: red;
  padding: 12px 12px 12px 24px;
  font-family: "Roboto";
  font-style: normal;
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  color: #303133;
}
.dropdownList {
  list-style-type: none;
}
</style>
