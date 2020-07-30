---
title: 準備您的環境
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 瞭解如何準備您的基礎結構以部署 Microsoft 團隊聊天室，讓您充分利用所有的功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d565cd500f22f86c19e38b531511eb25a5e1227a
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526699"
---
# <a name="prepare-your-environment"></a>準備您的環境

本節概述準備您的環境所需執行的步驟，讓您可以使用 Microsoft 團隊聊天室的所有功能。
  
1. 為每個 Microsoft 團隊聊天室主控台準備一個裝置帳戶。 如需詳細資訊，請參閱[部署 Microsoft 團隊會議室](rooms-deploy.md)。
    
2. 請確定有可供裝置使用的網路/網際網路連線正常。 
    
   - 它必須能夠使用 DHCP 接收 IP 位址。 （Microsoft 球隊會議室在第一次啟動時不能使用靜態 IP 位址進行設定，但之後可在裝置或上游交換器或路由器上設定此裝置的靜態 IP 位址。）
   - 它必須開啟這些埠（除了開啟媒體的一般埠之外）：
   - HTTPS：443
   - HTTP：80
   - 如果您的網路是透過 proxy 執行，您也需要 proxy 位址或腳本資訊。
    
     > [!IMPORTANT]
     > Microsoft 團隊聊天室不支援 proxy 驗證，因為它可能會干擾聊天室的常規操作。 在進入生產前，請先確認已免除來自 proxy 驗證的 Microsoft 團隊會議室。
  
3. 為了改善您的體驗，Microsoft 會收集資料。 若要允許 Microsoft 收集資料，請允許列出下列網站：

   - 遙測用戶端端點：https://vortex.data.microsoft.com/
   - [遙測設定] 端點：https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>建立並測試裝置帳戶

*裝置帳戶*是 Microsoft 團隊聊天室用戶端用來存取 Exchange 功能（例如行事曆），以及啟用商務用 Skype 的帳戶。 如需詳細資訊，請參閱[部署 Microsoft 團隊會議室](rooms-deploy.md)。
  
### <a name="check-network-availability"></a>檢查網路可用性

為了能正常運作，Microsoft 團隊聊天室裝置必須能夠存取符合這些需求的有線網路：
  
- 存取您的 Active Directory 或 Azure Active Directory （Azure AD）實例，以及您的 Microsoft Exchange 與商務用 Skype 伺服器。
- 存取可使用 DHCP 提供 IP 位址的伺服器。 在第一次啟動時，無法使用靜態 IP 位址來設定 Microsoft 團隊會議室。
- 存取 HTTP 埠80和443。
- TCP 和 UDP 埠已設定為適用于內部部署商務用 Skype 伺服器實現的[伺服器埠與通訊協定需求](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)，或 microsoft [365 和 Office 365 Url 以及](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)microsoft 團隊或商務用 SKYPE online 實現的 IP 位址範圍。

> [!IMPORTANT]
> 請務必使用有線 1 Gbps 網路連線，以確保您會有所需的頻寬。

> [!NOTE]
> Microsoft 團隊聊天室的軟體更新會自動從商務用 Microsoft 網上商店下載。 請參閱[Microsoft Store For Business 和教育版的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)，確認聊天室主機能夠存取商店及自我更新。
  
### <a name="certificates"></a>證書

您的 Microsoft 團隊聊天室裝置會使用 Exchange Web 服務、Microsoft 團隊或商務用 Skype、網路使用量和驗證的憑證。 如果相關伺服器使用公用憑證（適用于線上和某些內部部署的部署），系統管理員必須在安裝憑證的部分不需要採取進一步的動作。 另一方面，如果憑證授權單位是私人 CA （通常是內部部署部署），則裝置必須信任該 CA，這表示裝置上已安裝 CA + CA 鏈證書。 新增裝置至網域可能會自動執行此工作。
  
您可以按照與任何其他 Windows 用戶端相同的方式來安裝證書。 
  
> [!NOTE]
> 您可能需要證書，才能讓 Microsoft 團隊聊天室使用商務用 Skype 伺服器。
  
### <a name="proxy"></a>Proxy

Microsoft 團隊聊天室是設計來從 Windows 作業系統繼承 Proxy 設定。 以下列方式存取 Windows 作業系統：
  
1. 在 Microsoft [團隊聊天室] UI 中，按一下 [設定] 齒輪圖示，系統會在此提示您在裝置上提供本機系統管理員密碼（預設密碼為**sfb**）。
2. 按一下 [**設定**]，然後敲擊 [**移至 Windows** ] 按鈕，然後按 [**移**至系統管理員登入] 按鈕，然後按一下 [**管理員**] 按鈕（如果電腦已加入網域，請選擇 [**其他使用者]，** 然後使用 .\admin 做為使用者名稱）。
3. 在 regedit 中的 [**搜尋 Windows** ] 方塊的左下方類型（長按畫面或按一下滑鼠右鍵，然後選擇 [**以系統管理員身分執行**]）。
4. 按一下 [HKEY_USERS] 資料夾（您會看到一份電腦使用者 Sid 清單），確保已選取 [根資料夾] HKEY_USERS。
       
5. 按一下 [檔案]，然後選擇 [**載入 Hive]。**
6. 流覽至 [ **C:\Users\Skype** ] 資料夾，然後在 [檔案名] 方塊中輸入 NTUSER，然後按 [開啟] 按鈕

7. 系統會提示您輸入新載入的配置單元的索引鍵名;在 Skype 中輸入（您現在應該會看到 Skype 使用者的登錄設定）。
 
8. 開啟 Skype 金鑰並流覽至 [HKEY_USERS \Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 設定]，然後確保輸入這些設定： 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    如果 ProxyServer 不存在，您可能需要將此金鑰新增為字串，將 xx. xx：8080變更為您 Proxy 伺服器的 ip/主機和埠。
    
9. 完成變更之後，請醒目提示 Skype 使用者金鑰（Skype 的根資料夾），然後從 [登錄檔案] 功能表中選擇 [卸載 Hive] （系統會提示您確認-選取 **[是]** ）。
    
10. 您現在可以關閉 [登錄編輯程式]，然後在 Windows 搜尋方塊中輸入 [登出]。
    
11. 回到登入畫面，選擇**Skype**使用者。 如果上述所有步驟都已成功完成，Microsoft 團隊聊天室裝置將會順利登入。
    
若要使用此應用程式，您必須能夠連線到下方所述的端點。 若要查看 IP 位址，請展開描述流量流程之資料表下方的 [IP 位址] 區段。
  
**防火牆 Proxy 主機名稱/埠範例**

|特殊|來源或認證|來源埠|目的地|CDN|適用于 Office 365 的 ExpressRoute|目的地 IP|目的地埠|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|驗證與身分識別  <br/> |請參閱[Microsoft 365 和 Office 365 驗證與身分識別](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|入口網站與共享  <br/> |請參閱[Microsoft 365 系統管理中心及共用](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|SIP 信號  <br/> |用戶端電腦或登入的使用者  <br/> |暫時埠  <br/> |\*. contoso.com  <br/> |否  <br/> |是  <br/> |[商務用 Skype IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|持續性共用物件模型（PSOM）連線 web 會議  <br/> |用戶端電腦或登入的使用者  <br/> |暫時埠  <br/> |\*. contoso.com  <br/> |否  <br/> |是  <br/> |[商務用 Skype IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS 下載  <br/> |用戶端電腦或登入的使用者  <br/> |暫時埠  <br/> |\*. contoso.com  <br/> |否  <br/> |是  <br/> |[商務用 Skype IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|音訊  <br/> |用戶端電腦或登入的使用者  <br/> |TCP/UDP 50000-50019  <br/> |\*. contoso.com  <br/> |否  <br/> |是  <br/> |[商務用 Skype IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50000-59999  <br/> |
|影片  <br/> |用戶端電腦或登入的使用者  <br/> |TCP/UDP 50020-50039  <br/> |\*. contoso.com  <br/> |否  <br/> |是  <br/> |[商務用 Skype IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443、UDP 3478、TCP/UDP 50000-59999  <br/> |
|桌面共用  <br/> |用戶端電腦或登入的使用者  <br/> |TCP/UDP 50040-50059  <br/> |\*. contoso.com  <br/> |否  <br/> |是  <br/> |[商務用 Skype IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443，50000-59999  <br/> |
|在 iOS 裝置上 Lync mobile 2010 的 lync Mobile 推播通知。 您不需要 Android、Nokia Symbian 或 Windows Phone 行動裝置。  <br/> |用戶端電腦或登入的使用者  <br/> |暫時埠  <br/> |\*. contoso.com  <br/> |否  <br/> |是  <br/> |[商務用 Skype IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype 遙測  <br/> |用戶端電腦或登入的使用者  <br/> |暫時埠  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |否  <br/> |否  <br/> |不適用  <br/> |TCP 443  <br/> |
|Skype 用戶端快速秘訣  <br/> |用戶端電腦或登入的使用者  <br/> |暫時埠  <br/> |quicktips.skypeforbusiness.com  <br/> |否  <br/> |否  <br/> |不適用  <br/> |TCP 443  <br/> |

> [!NOTE]
> Contoso.com 和 broadcast.skype.com 的萬用字元代表一個長清單，這些節點專供 Microsoft 365 或 Office 365 使用。 
  
### <a name="create-provisioning-packages"></a>建立預配套件

您將會使用 [預配套件] 來驗證 Exchange Server、Microsoft 365 或 Office 365。
  
### <a name="admin-group-management"></a>管理員群組管理

加入網域之後，您可以使用 [群組原則] 或 [本機電腦管理]，將安全性群組設定為本機管理員，就像您在網域中的 Windows 電腦一樣。 屬於該安全群組成員的任何人都可以輸入其認證及解除鎖定設定。
  
> [!NOTE]
> 如果您的 Microsoft 團隊聊天室裝置無法與網域失去信任（例如，如果您在網域加入後從網域中移除 Microsoft 團隊聊天室），您將無法在裝置上進行驗證，也無法開啟 [設定]。 解決方法是使用本機管理員帳戶登入。 
  
## <a name="local-accounts"></a>本機帳戶

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft 團隊聊天室本機使用者帳戶

裝置帳戶通常不會使用密碼。 您可以為它提供密碼，但會產生一些後果，包括使用者可能在密碼到期時封鎖主控台應用程式的可能性。 因此，管理員應該採取的行動，以確保不允許密碼過期。
  
### <a name="admin---local-administrator-account"></a>"管理員"-本機系統管理員帳戶

Microsoft 團隊會議室預設密碼設定為 "sfb"。 若要在本機變更密碼，請移至 [Windows 設定] \> ，移至 [windows] 或 AutoUnattend.xml 檔案（使用 ADK 的 Windows 系統影像管理員來變更 xml 檔案）。
  
> [!CAUTION]
> 請務必儘快變更 Microsoft 團隊會議室密碼。 
  
您也可以設定網域管理員設為「本機管理員」的群群組原則，來管理本機系統管理員密碼。
  
在安裝期間，不會將本機系統管理員密碼作為選項包含。
  
### <a name="machine-account"></a>電腦帳戶

與任何 Windows 裝置一樣，您可以在 [ \> 重新命名電腦] 的 [設定] 中以滑鼠右鍵按一下來重新命名電腦名稱稱 \> 。
  
 如果您想要在加入到網域之後重新命名電腦，請使用重新命名電腦 PowerShell 命令，後面接著電腦的新名稱。
  
## <a name="related-topics"></a>相關主題

[規劃 Microsoft 團隊聊天室](rooms-plan.md)

[Microsoft Teams 會議室需求](requirements.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft Store for Business 和教育版的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
