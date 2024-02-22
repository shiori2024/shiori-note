<template>
  <!-- 大盒子 -->
  <n-flex class="container" :vertical="true">
    <!-- 导航 -->
    <n-flex class="top">
      <n-flex class="nav" justify="space-between" align="center">
        <div class="info">
          <!-- 菜单按钮 -->
          <!-- 原生按钮 <n-switch v-model:value="collapsed" /> -->
          <n-button circle @click="collapsed = !collapsed">
            <n-icon size="20" color="#0e7a0d">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                <path fill="currentColor" d="M3 6h18v2H3zm0 5h18v2H3zm0 5h18v2H3z" />
              </svg>
            </n-icon>
          </n-button>
          <!-- 云端按钮 -->
          <n-button circle>
            <n-icon size="20" color="#0e7a0d">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                <path fill="currentColor"
                  d="M6.5 20q-2.28 0-3.89-1.57Q1 16.85 1 14.58q0-1.95 1.17-3.48q1.18-1.53 3.08-1.95q.63-2.3 2.5-3.72Q9.63 4 12 4q2.93 0 4.96 2.04Q19 8.07 19 11q1.73.2 2.86 1.5q1.14 1.28 1.14 3q0 1.88-1.31 3.19T18.5 20Z" />
              </svg>
            </n-icon>
          </n-button>
          <!-- 前进按钮 -->
          <n-button circle @click="$router.back()">
            <n-icon size="20" color="#0e7a0d">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                <path fill="currentColor" d="M20 11v2H8l5.5 5.5l-1.42 1.42L4.16 12l7.92-7.92L13.5 5.5L8 11z" />
              </svg>
            </n-icon>
          </n-button>
          <!-- 后退按钮 -->
          <n-button circle @click="$router.go(-1)">
            <n-icon size="20" color="#0e7a0d">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                <path fill="currentColor" d="M4 11v2h12l-5.5 5.5l1.42 1.42L19.84 12l-7.92-7.92L10.5 5.5L16 11z" />
              </svg>
            </n-icon>
          </n-button>

        </div>
        <div class="title">
          <n-gradient-text :size="16" type="success" gradient="linear-gradient(60deg, green 0%, green 40%, blue 100%)">
            shiori-note
          </n-gradient-text>
        </div>
        <div class="config">
          <n-button circle>
            <n-icon size="20" color="#0e7a0d">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                <path fill="currentColor"
                  d="M9.5 3A6.5 6.5 0 0 1 16 9.5c0 1.61-.59 3.09-1.56 4.23l.27.27h.79l5 5l-1.5 1.5l-5-5v-.79l-.27-.27A6.516 6.516 0 0 1 9.5 16A6.5 6.5 0 0 1 3 9.5A6.5 6.5 0 0 1 9.5 3m0 2C7 5 5 7 5 9.5S7 14 9.5 14S14 12 14 9.5S12 5 9.5 5" />
              </svg>
            </n-icon>
          </n-button>
          <n-config-provider :theme="theme">
            <n-button @click="handTheme" circle>
              <n-icon size="20" color="#0e7a0d">
                <template v-if="themetit === '暗色主题'">
                  <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                    <path fill="currentColor"
                      d="m3.55 19.09l1.41 1.41l1.8-1.79l-1.42-1.42M12 6c-3.31 0-6 2.69-6 6s2.69 6 6 6s6-2.69 6-6c0-3.32-2.69-6-6-6m8 7h3v-2h-3m-2.76 7.71l1.8 1.79l1.41-1.41l-1.79-1.8M20.45 5l-1.41-1.4l-1.8 1.79l1.42 1.42M13 1h-2v3h2M6.76 5.39L4.96 3.6L3.55 5l1.79 1.81zM1 13h3v-2H1m12 9h-2v3h2" />
                  </svg>
                </template>
                <template v-else>
                  <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                    <path fill="currentColor"
                      d="m17.75 4.09l-2.53 1.94l.91 3.06l-2.63-1.81l-2.63 1.81l.91-3.06l-2.53-1.94L12.44 4l1.06-3l1.06 3zm3.5 6.91l-1.64 1.25l.59 1.98l-1.7-1.17l-1.7 1.17l.59-1.98L15.75 11l2.06-.05L18.5 9l.69 1.95zm-2.28 4.95c.83-.08 1.72 1.1 1.19 1.85c-.32.45-.66.87-1.08 1.27C15.17 23 8.84 23 4.94 19.07c-3.91-3.9-3.91-10.24 0-14.14c.4-.4.82-.76 1.27-1.08c.75-.53 1.93.36 1.85 1.19c-.27 2.86.69 5.83 2.89 8.02a9.96 9.96 0 0 0 8.02 2.89m-1.64 2.02a12.08 12.08 0 0 1-7.8-3.47c-2.17-2.19-3.33-5-3.49-7.82c-2.81 3.14-2.7 7.96.31 10.98c3.02 3.01 7.84 3.12 10.98.31" />
                  </svg>
                </template>
              </n-icon>
            </n-button>
            <n-global-style />
          </n-config-provider>
        </div>
      </n-flex>
    </n-flex>
    <!-- 主体 -->
    <n-flex class="main" justify="start">
      <!-- 菜单栏 -->
      <div class="left">
        <div class="menu">
          <n-layout has-sider>
            <n-layout-sider bordered collapse-mode="width" :collapsed-width="64" :width="240" :collapsed="collapsed"
              show-trigger @collapse="collapsed = true" @expand="collapsed = false">
              <n-menu :collapsed="collapsed" :collapsed-width="64" :collapsed-icon-size="22" :options="menuOptions" />
            </n-layout-sider>
          </n-layout>
        </div>
      </div>
      <!-- 工作区 -->
      <div class="right">
        <div class="tabs">
          <n-tabs v-model:value="value" type="card" :addable="addable" :closable="closable" tab-style="min-width: 80px;"
            @close="handleClose" @add="handleAdd">
            <n-tab-pane v-for="panel in panels" :key="panel" :name="panel">
              <!-- {{ panel }} -->
              <n-breadcrumb>
                <n-breadcrumb-item separator=">" v-for="panel in panels" :key="panel">我是面包屑</n-breadcrumb-item>
              </n-breadcrumb>
            </n-tab-pane>
          </n-tabs>
        </div>
      </div>
    </n-flex>
    <!-- 底部 -->
    <n-flex class="bottom" justify="space-between">
      <span class="pd10">最后保存:<n-time time-zone="Asia/shanghai" format="yyyy-MM-dd hh:mm:ss" /></span>
      <span class="pd10">Line: 1 | words: 1024</span>
    </n-flex>
  </n-flex>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue'
import { darkTheme } from 'naive-ui'
import type { MenuOption } from 'naive-ui'

export default defineComponent({
  setup() {
    // 主题变量
    const theme = ref<any>(null)
    // 主体按钮title
    const themetit = ref<string>("暗色主题")
    // 菜单展开，默认不展开
    const menuStatus = ref<boolean>(false)

    const menuOptions: MenuOption[] = [
      {
        label: '且听风吟',
        key: 'hear-the-wind-sing',
        href: 'https://baike.baidu.com'
      },
      {
        label: '1973年的弹珠玩具',
        key: 'pinball-1973',
        disabled: true,
        children: [
          {
            label: '鼠',
            key: 'rat'
          }
        ]
      },
      {
        label: '寻羊冒险记',
        key: 'a-wild-sheep-chase',
        disabled: true
      },
      {
        label: '舞，舞，舞',
        key: 'dance-dance-dance',
        children: [
          {
            type: 'group',
            label: '人物',
            key: 'people',
            children: [
              {
                label: '叙事者',
                key: 'narrator'
              },
              {
                label: '羊男',
                key: 'sheep-man'
              }
            ]
          },
          {
            label: '饮品',
            key: 'beverage',
            children: [
              {
                label: '威士忌',
                key: 'whisky',
                href: 'https://baike.baidu.com/item/%E5%A8%81%E5%A3%AB%E5%BF%8C%E9%85%92/2959816?fromtitle=%E5%A8%81%E5%A3%AB%E5%BF%8C&fromid=573&fr=aladdin'
              }
            ]
          },
          {
            label: '食物',
            key: 'food',
            children: [
              {
                label: '三明治',
                key: 'sandwich'
              }
            ]
          },
          {
            label: '过去增多，未来减少',
            key: 'the-past-increases-the-future-recedes'
          }
        ]
      }
    ]

    const valueRef = ref(1)
    const panelsRef = ref([1, 2, 3, 4, 5])
    const addableRef = computed(() => {
      return {
        disabled: panelsRef.value.length >= 10
      }
    })
    const closableRef = computed(() => {
      return panelsRef.value.length > 1
    })

    return {
      theme,
      themetit,
      menuStatus,
      menuOptions,
      darkTheme,
      collapsed: ref(true),
      value: valueRef,
      panels: panelsRef,
      addable: addableRef,
      closable: closableRef,
      handTheme() {
        theme.value = theme.value == null ? darkTheme : null
        themetit.value = themetit.value === "浅色主题" ? "暗色主题" : "浅色主题"
      },
      handleMenuHidden() {
        menuStatus.value = !menuStatus.value
        console.log(menuStatus.value)
        if (menuStatus.value) {
          document.body.style.overflow = "hidden"
        } else {
          document.body.style.overflow = "auto"
        }
      },
      handleAdd() {
        const newValue = Math.max(...panelsRef.value) + 1
        panelsRef.value.push(newValue)
        valueRef.value = newValue
      },
      handleClose(name: number) {
        const { value: panels } = panelsRef
        const nameIndex = panels.findIndex((panelName) => panelName === name)
        if (!~nameIndex) return
        panels.splice(nameIndex, 1)
        if (name === valueRef.value) {
          valueRef.value = panels[Math.min(nameIndex, panels.length - 1)]
        }
      }
    }
  }
})
</script>

<style scoped>
.nav {
  width: 100%;
  height: 50px;
  padding: 0px;
  line-height: 100%;
  background: var(--color-primary);
}

.pd10 {
  padding: 20px;
}

.tabs {
  width: 1200px;
  height: 800px;
}

.config {
  display: flex;
  justify-content: center;
  align-items: center;
}

.bottom {
  position: absolute;
  bottom: 0px;
  width: 100%;
  height: 50px;
}
</style>