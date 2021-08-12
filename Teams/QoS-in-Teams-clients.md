---
title: 在用戶端中 (QoS) 服務品質Microsoft Teams品質
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何使用 QoS (服務品質) 優化桌面用戶端Microsoft Teams網路流量。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: efe36f1ada9e8c98a82d8d5ece0cee2d9058aa318ef174f6d1b704f1c7f1e178
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282886"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>在用戶端中 (QoS) 服務品質Microsoft Teams品質

您可以在群組原則內使用以策略為基礎的服務品質 (QoS) ，在用戶端中設定預先定義的 DSCP 值的來源Teams範圍。 下表指定的埠範圍是為每個工作負載建立策略的起點。

*表格 1.建議的初始埠範圍*

|媒體流量類型| 用戶端來源連接埠範圍  |通訊協定|DSCP 值|DSCP 類別|
|:--- |:--- |:--- |:--- |:--- |
|音訊| 50,000-50,019|TCP/UDP|46|快速式轉送 (EF)|
|影片| 50,020-50,039|TCP/UDP|34|保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059|TCP/UDP|18|保證式轉送 (AF21)|
| | | | | |

盡可能在群組原則物件中設定以策略為基礎的 QoS 設定。 下列步驟與在 商務用 Skype Server[](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)上為用戶端組定埠範圍和服務品質政策非常類似，其中可能不需要一些額外的詳細資料。

若要為已加入網域的電腦Windows 10 QoS 音訊策略，首先請登入已安裝群組原則管理的電腦。 開啟群組原則管理 (按一下 [開始>、指向 [管理工具，然後按一下群組原則管理) ，然後完成下列步驟：

1. 在群組原則管理中，找出應建立新策略的容器。 例如，如果您所有的用戶端電腦都位於名為 Client 的 OU中，則新策略應在用戶端 OU 中建立。

1. 以滑鼠右鍵按一下適當的容器，然後按一下 [在此網域中建立 **GPO，然後在這裡連結它**。

1. 在 [ **新增 GPO」** 對話方塊中，在 [名稱> 方塊中輸入新群組原則 **物件的名稱，** 然後按一下 [ **確定**。

1. 以滑鼠右鍵按一下新建立的政策，然後按一下 [ **編輯**。

1. 在群組原則管理編輯器中，展開[電腦群組Windows 設定，以滑鼠 **右** 鍵按一下 [以策略為基礎的 **QoS，** 然後按一下 [**建立新策略**> 。

1. 在 [ **以策略為基礎的 QoS** 對話方塊的開啟頁面上，在 [名稱> 方塊中輸入新 **政策** 的名稱。 選取 **指定 DSCP 值** ，然後將值設為 **46**。 請 **離開 [未指定外發節** 流速率，然後按一下 [下 **一步**）。

1. 在下一頁中，選取 [只有 **具有此可執行** 檔案名稱的應用程式，然後輸入 **Teams.exe名稱，** 然後按一下 [ **下一步**。 此設定會指示策略只排列來自用戶端之Teams流量的優先順序。

1. 請確定第三頁上已選取 [任何來源 **IP 位址** 及任何目的地 **IP** 位址，然後按一下 [下 **一步**> 。 這兩個設定可確保無論哪部電腦 (IP 位址) 封包，以及哪個電腦 (IP 位址) 都會受到管理。

1. 第四頁，從選取此 **QoS** 原則適用于下拉式清單的通訊協定，選取 TCP 和 **UDP。** TCP (傳輸控制通訊) 和 UDP (使用者資料包通訊) 是最常用的兩種網路通訊協定。

1. 在標題下 **指定來源埠號碼**，選取 **從此來源埠或範圍**。 在隨附的文字方塊中，輸入音訊廣播所保留的埠範圍。 例如，如果您透過埠 50019 為音訊流量保留埠 50000，請使用此格式輸入埠範圍 **：50000：50019**。 按一下 **[完成>**。

1. 重複步驟 5-10 以建立視像與應用程式/桌面共用的政策，以步驟 6 和 10 中的適當值來表示。

在用戶端電腦上重新更新群組原則之前，您建立的新政策不會生效。 雖然群群組原則會自行定期重新更新，但您可以遵循下列步驟來強制立即重新建立：

1. 在您想要重新更新群組原則的每部電腦上，開啟以系統管理員 (*以系統管理員*) 。

1. 在命令提示符中，輸入

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>驗證群組原則物件中的 DSCP 標記

若要確認已設定群組原則物件的值，請執行下列步驟：

1. 開啟以系統管理員 (*命令提示*) 。

1. 在命令提示符中，輸入

   ```console
   gpresult /R > gp.txt
   ```

   這會產生已申請的 GPO 報告，並將它傳送至名為 *gp.txt* 的文字檔。

   針對名為gp.html 的可讀 *HTML* 報表，請輸入下列命令：

   ```console
   gpresult /H gp.html
   ```

1. 在產生的檔案中，尋找標題為已應用組 **策略** 物件，並確認先前建立之群組原則物件的名稱在已應用原則清單中。

1. 開啟登錄編輯程式，然後前往

   HKEY \_ LOCAL \_ MACHINE \\ 軟體政策 Microsoft Windows \\ \\ \\ \\ QoS

   確認資料表 2 中列出的登錄機碼目值。

   *表格 2.QoS Windows登錄機碼目的值*

   |          名稱          |  類型  |    資料     |
   |         :---:          | :---:  |    :---:    |
   |    應用程式名稱    | REG_SZ |  Teams.exe  |
   |       DSCP 值       | REG_SZ |     46      |
   |        本地 IP        | REG_SZ |     \*      |
   | 本地 IP 前置長度 | REG_SZ |     \*      |
   |       本地埠       | REG_SZ | 50000-50019 |
   |        Protocol (通訊協定)        | REG_SZ |     \*      |
   |       遠端 IP        | REG_SZ |     \*      |
   |    遠端 IP 首碼    | REG_SZ |     \*      |
   |      遠端埠       | REG_SZ |     \*      |
   |     節流速率      | REG_SZ |     -1      |
   | | | |

1. 確認您使用之用戶端的應用程式名稱專案值正確無誤，並確認 DSCP 值和本地埠專案都反映群組原則物件中的設定。


## <a name="related-topics"></a>相關主題

[在 (中 (QoS) 服務品質Teams](QoS-in-Teams.md)