---
title: '在 Microsoft Teams 用戶端中實作服務品質 (QoS) '
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 瞭解如何使用 QoS (服務品質) 優化 Microsoft Teams 桌面用戶端的網路流量。
ms.localizationpriority: medium
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
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563921"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>在 Microsoft Teams 用戶端中實作服務品質 (QoS) 

您可以在 群組原則 內使用原則型服務品質 (QoS) ，為 Teams 用戶端中預先定義的 DSCP 值設定來源埠範圍。 下表中指定的埠範圍是建立每個工作負載原則的起點。

*資料表 1.建議的初始埠範圍*

|媒體流量類型| 用戶端來源連接埠範圍  |通訊協定|DSCP 值|DSCP 類別|
|:--- |:--- |:--- |:--- |:--- |
|音訊| 50,000-50,019|TCP/UDP|46|快速式轉送 (EF)|
|影片| 50,020-50,039|TCP/UDP|34|保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059|TCP/UDP|18|保證式轉送 (AF21)|
| | | | | |

請盡可能在群組原則物件內設定原則型 QoS 設定。 下列步驟與在[商務用 Skype Server 上為用戶端設定埠範圍和服務品質](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)原則非常類似，其中包含一些不需要的額外詳細資料。

若要為加入網域的Windows 10電腦建立 QoS 音訊原則，請先登入已安裝群組原則管理的電腦。 開啟 [群組原則管理] (按一下 [開始]，指向 [管理工具]，然後按一下 [群組原則管理]) ，然後完成下列步驟：

1. 在 [群組原則管理] 中，找出應建立新原則的容器。 例如，如果您所有的用戶端電腦都位於名為 [ **客戶** 端] 的 OU 中，則應在 [用戶端 OU] 中建立新原則。

1. 以滑鼠右鍵按一下適當的容器，然後按一下 [ **在此網域中建立 GPO]，然後將它連結在這裡**。

1. 在 [**新增 GPO**] 對話方塊的 [名稱] 方塊中，輸入新群組原則 **物件的名稱**，然後按一下 [**確定]**。

1. 以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯]**。

1. 在 [群組原則管理編輯器] 中，展開 [**電腦設定**]，展開 **[Windows 設定**]，以滑鼠右鍵按一下 [原則 **型 QoS]**，然後按一下 [**建立新原則]**。

1. 在 [ **原則型 QoS]** 對話方塊的開啟頁面上，于 [ **名稱** ] 方塊中輸入新原則的名稱。 選 **取 [指定 DSCP 值** ]，並將值設為 **46**。 離開 指定未選取 **的輸出節流速率** ，然後按 [ **下一步]**。

1. 在下一個頁面上，選取 **[只有具有此可執行名稱的應用程式** ]，然後 **輸入名稱Teams.exe**，然後按 [ **下一步]**。 此設定會指示原則只排定 Teams 用戶端的比對流量優先順序。

1. 請確認已選取第三頁上的 [ **任何來源 IP 位址** ] 和 [ **任何目的地 IP 位址** ]，然後按 [ **下一步]**。 這兩個設定可確保無論哪部電腦 (IP 位址) 傳送封包，以及哪些電腦 (IP 位址) 會收到封包，封包都會受到管理。

1. 在 [第四頁] 上，從 [選取 **此 QoS 原則適用于** 下拉式清單的通訊協定] 中選取 **[TCP 和 UDP**]。 TCP (傳輸控制通訊協定) 和 UDP (使用者資料圖表通訊協定) 是兩種最常使用的網路通訊協定。

1. 在 [ **指定來源埠號碼**] 標題底下，選 **取 [從此來源埠或範圍]**。 在隨附的文字方塊中，輸入保留用於音訊廣播的埠範圍。 例如，如果您保留埠 50000 至埠 50000 以供音訊流量使用，請使用此格式輸入埠範圍： **50000：50019**。 按一下 [ **完成]**。

1. 重複步驟 5-10 以建立視訊和應用程式/桌面共用的原則，在步驟 6 和 10 中取代適當的值。

您建立的新原則必須等到用戶端電腦重新整理群組原則才會生效。 雖然群組原則定期自行重新整理，但您可以依照下列步驟強制立即重新整理：

1. 在您要重新整理群組原則的每部電腦上，以系統管理員身分開啟命令提示字元 (*以系統管理員身* 分執行) 。

1. 在命令提示字元中，輸入

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>確認群組原則物件中的 DSCP 標記

若要確認已設定群組原則物件的值，請執行下列步驟：

1. 以系統管理員身分開啟命令提示字元 (*以系統管理員* 身分執行) 。

1. 在命令提示字元中，輸入

   ```console
   gpresult /R > gp.txt
   ```

   這會產生已套用 GPO 的報告，並將它傳送到名為 *gp.txt* 的文字檔。

   如需更易於閱讀且名為gp.html的 HTML 報 *表*，請輸入下列命令：

   ```console
   gpresult /H gp.html
   ```

1. 在產生的檔案中，尋找 [套用 **群組原則物件**] 標題，並確認先前建立的群組原則物件名稱在套用原則清單中。

1. 開啟 [登錄編輯程式]，然後移至

   HKEY \_ LOCAL \_ MACHINE \\ Software \\ Policies \\ Microsoft \\ Windows \\ QoS

   確認資料表 2 中所列登錄專案的值。

   *資料表 2.QoS 的 Windows 登錄專案值*

   |          名稱          |  類型  |    資料     |
   |         :---:          | :---:  |    :---:    |
   |    應用程式名稱    | REG_SZ |  Teams.exe  |
   |       DSCP 值       | REG_SZ |     46      |
   |        本機 IP        | REG_SZ |     \*      |
   | 本機 IP 前置長度 | REG_SZ |     \*      |
   |       本機埠       | REG_SZ | 50000-50019 |
   |        Protocol (通訊協定)        | REG_SZ |     \*      |
   |       遠端 IP        | REG_SZ |     \*      |
   |    遠端 IP 首碼    | REG_SZ |     \*      |
   |      遠端埠       | REG_SZ |     \*      |
   |     節流速率      | REG_SZ |     -1      |
   | | | |

1. 確認您所使用之用戶端的應用程式名稱專案值正確無誤，並確認 DSCP 值和本機埠專案都反映群組原則物件中的設定。


## <a name="related-topics"></a>相關主題

[在 Teams 中實作服務品質 (QoS) ](QoS-in-Teams.md)