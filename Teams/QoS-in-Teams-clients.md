---
title: 在 Microsoft 團隊用戶端中實施服務品質
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 實施 Microsoft 團隊用戶端的服務品質（QoS）。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28e6664fa43819493e5b9e02d182bcec44f00905
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572560"
---
# <a name="set-qos-on-windows-clients"></a>在 Windows 用戶端上設定 QoS

您可以在 [群組原則] 中使用原則式 QoS，在團隊用戶端中設定預先定義 DSCP 值的來源埠範圍。 下表中指定的埠範圍是為每個工作負載建立原則的起點。

_建議的初始埠範圍_

媒體流量類型| 用戶端來源埠範圍 |通訊協定|DSCP 值|DSCP 類別|
|:--- |:--- |:--- |:--- |:--- |
|音訊| 50000–50019|TCP/UDP|46|加急轉移（EF）|
|顯示器| 50,020–50,039|TCP/UDP|34|有保證的轉寄（AF41）|
|應用程式/螢幕共用| 50,040–50,059|TCP/UDP|滿|有保證的轉寄（AF21）|
| | | | |

請盡可能在群群組原則物件中設定原則式 QoS 設定。 下列步驟與[在商務用 Skype Server 上針對您的用戶端設定埠範圍和服務品質原則](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)非常相似，這也有一些其他可能不必要的詳細資料。

若要為加入網域的 Windows 10 電腦建立 QoS 音訊原則，請先登入已安裝群組原則管理的電腦。 開啟 [群組原則管理] （按一下 [開始]，指向 [系統管理工具]，然後按一下 [群組原則管理]），然後完成下列步驟：

1. 在 [群組原則管理] 中，找出要建立新原則的容器。 例如，如果所有用戶端電腦都位於一個名為「**用戶端**」的 OU 中，則應該在用戶端 OU 中建立新的原則。

2. 以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域建立 GPO]，然後在這裡連結**。

3. 在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱，然後按一下 **[確定]**。

4. 以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。

5. 在 [群組原則管理編輯器] 中，展開 [**電腦**設定]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。

6. 在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱。 選取 [**指定 DSCP 值**]，然後將值設定為**46**。 [離開]**指定輸出限制率**未選取，然後按 **[下一步]**。

7. 在下一頁中，選取 [**僅限具有此可執行檔名稱的應用程式**]，然後輸入名稱 [**團隊 .exe**]，然後按 **[下一步]**。 此設定會指示原則只會將小組用戶端的流量相符的優先順序。

8. 在第三個頁面上，確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**]，然後按一下 **[下一步]**。 這兩項設定可確保無論哪個電腦（IP 位址）傳送資料包，以及哪台電腦（IP 位址）會接收資料包，都會管理資料包。

9. 在第四頁，從 [**選取此 QoS 原則套用至下列協定**] 下拉式清單中選取 [ **TCP 和 UDP** ]。 TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是兩種最常使用的網路通訊協定。

10. 在 [標題] 底下，**指定來源埠號**，選取 [**從此來源埠或範圍**]。 在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。 例如，如果您是透過埠50019將埠50000保留音訊流量，請輸入使用此格式的埠範圍： **50000:50019**。 按一下 **[完成]**。

11. 重複步驟5-10 來建立影片和應用程式/桌面共用的原則，在步驟6和10中取代適當的值。

在用戶端電腦上重新整理 [群組原則] 之前，您所建立的新原則將不會生效。 雖然群組原則會定期自行進行重新整理，但是您可以遵循下列步驟強制立即重新整理：

1. 在您要重新整理群組原則的每個電腦上，開啟命令主控台。 確定命令主控台已設定為以系統管理員身分執行。

2. 在命令提示字元中，輸入

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>驗證群群組原則物件中的 DSCP 標記

若要確認已設定群組原則物件的值，請執行下列步驟。

1. 開啟命令主控台。 確定命令主控台已設定為以系統管理員身分執行。

2. 在命令提示字元中，輸入：

   ``` powershell
   gpresult /R > gp.txt
   ```

   這會產生報告並將它傳送到名為 gp 的文字檔。 或者，您也可以輸入下列命令，以在名為 gp 的 HTML 報表中產生相同的資料。

   ``` powershell
   gpresult /H >gp.html
   ```

   ![運行 gpresult 命令之主控台視窗的螢幕擷取畫面。](media/Qos-in-Teams-Image3.png "運行 gpresult 命令之主控台視窗的螢幕擷取畫面。")

3. 在產生的檔案中，尋找標題套用的**群組原則物件**，並確認在已套用的原則清單中，先前建立的群組原則物件名稱。

4. 開啟 [登錄編輯程式]，然後移至：

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   確認資料表4中所列的登錄專案值。

   _資料表4。QoS 的 Windows 登錄專案值_

   |          名稱          |  類型  |    資料     |
   |         :---:          |:---:   |    :---:    |
   |    應用程式名稱    | REG_SZ |  團隊 .exe  |
   |       DSCP 值       | REG_SZ |     46      |
   |        本機 IP        | REG_SZ |     \*      |
   | 本機 IP 前置詞長度 | REG_SZ |     \*      |
   |       本機埠       | REG_SZ | 50000-50019 |
   |        通訊協定        | REG_SZ |     \*      |
   |       遠端 IP        | REG_SZ |     \*      |
   |    遠端 IP 首碼    | REG_SZ |     \*      |
   |      遠端埠       | REG_SZ |     \*      |
   |     節流率      | REG_SZ |     -1      |

5. 針對您正在使用的用戶端，確認 [應用程式名稱] 專案的值正確無誤，然後確認 [DSCP 值] 和 [本機埠] 專案都反映了 [群組原則] 物件中的設定。
