---
title: 準備您的環境
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 瞭解如何準備您的基礎結構以部署Microsoft Teams 會議室讓您可以善用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b04ecd5b10f82e3f331bc2e888f59927de52e18c
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2022
ms.locfileid: "64838994"
---
# <a name="prepare-your-environment"></a>準備您的環境

本節包含準備環境所需的步驟概觀，以便您可以使用Microsoft Teams 會議室的所有功能。
  
1. 為每個Microsoft Teams 會議室主機準備資源帳戶。 如需詳細資訊，請參閱[部署Microsoft Teams 會議室](rooms-deploy.md)。
    
2. 確定有正常運作的網路/網際網路連線供裝置使用。
  
3. 為了改善您的體驗，Microsoft 會收集資料。 若要允許 Microsoft 收集資料，請允許下列網站：

   - 遙測用戶端端點： https://vortex.data.microsoft.com/
   - 遙測設定端點： https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-resource-account"></a>建立和測試資源帳戶

*資源帳戶* 是Microsoft Teams 會議室用戶端用來存取行事曆等Exchange功能，以及連線至Microsoft Teams的帳戶。 如需詳細資訊，請參閱[部署Microsoft Teams 會議室](rooms-deploy.md)。
  
### <a name="check-network-availability"></a>檢查網路可用性

若要正常運作，Microsoft Teams 會議室必須能夠存取符合下列需求的有線網路：
  
- 存取您的 Active Directory 或 Azure Active Directory (Azure AD) 實例，以及 Microsoft Exchange和Microsoft Teams。

- 存取可使用 DHCP 提供 IP 位址的伺服器。 Microsoft Teams 會議室無法在第一個單位啟動時使用靜態 IP 位址進行設定。

- 存取 HTTP 埠 80 和 443。

- TCP 和 UDP 埠的設定方式，如內部部署商務用 Skype Server實作之伺服器的埠[和通訊協定需求](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)所述，或Microsoft 365[和Office 365網址和 Microsoft Teams IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)。

如果您的網路是透過 Proxy 執行，您也需要 Proxy 位址或腳本資訊。
    
> [!IMPORTANT]
> Microsoft Teams 會議室不支援 Proxy 驗證，因為它可能會干擾聊天室的一般操作。 進入生產之前，請確定Microsoft Teams 會議室已免除 Proxy 驗證。

> [!IMPORTANT]
> 請務必使用有線 1 Gbps 網路連線，以確保您擁有所需的頻寬。

> [!NOTE]
> 系統會自動從商務用 Microsoft Store下載Microsoft Teams 會議室軟體更新。 請參閱[商務用 Microsoft Store和教育版的先決條件](/microsoft-store/prerequisites-microsoft-store-for-business)，以確認會議室主機是否能存取商店並自行更新。
  
### <a name="certificates"></a>證書

您的Microsoft Teams 會議室裝置會使用Exchange Web 服務、Microsoft Teams或商務用 Skype、網路使用方式和驗證的憑證。 如果相關伺服器使用公用憑證，即線上和某些內部部署的情況，則系統管理員不必採取進一步的動作來安裝憑證。 另一方面，如果憑證授權單位單位是私人 CA，則裝置必須信任該 CA。 這表示裝置上已安裝 CA + CA 鏈結憑證。 將裝置新增至網域可能會自動執行這項工作。
  
您安裝憑證的方式與安裝任何其他Windows用戶端的方式相同。

> [!IMPORTANT]
> 如果您的 Proxy 伺服器使用內部簽署的憑證，您必須在Microsoft Teams 會議室裝置上安裝內部憑證鏈結，包括根 CA。
  
> [!NOTE]
> 您可能需要憑證才能使用Microsoft Teams 會議室商務用 Skype Server。
  
### <a name="proxy"></a>代理

Microsoft Teams 會議室是設計來繼承 Windows OS 的 Proxy 設定。 以下列方式存取Windows作業系統：
  
1. 在 Microsoft Teams 會議室 UI 中，按一下設定齒輪圖示，系統會提示您輸入裝置上的本機系統管理員密碼， (預設密碼為 **sfb**) 。
2. 點 **選設定**，接著點選 [**移至Windows**] 按鈕，然後點選 [移 **至系統管理員登** 入] 按鈕，然後按一下 [系統 **管理員**] 按鈕 (如果電腦已加入網域，請選擇 [**其他使用者]，** 然後使用 .\admin 做為使用者名稱) 。
3. 在 regedit 左下方的 [**搜尋Windows**] 方塊中 (長按螢幕或以滑鼠右鍵按一下，然後選擇 [**以系統管理員身** 分執行]) 。
4. 按一下HKEY_USERS資料夾 (您會看到機器使用者 SIM 卡清單，) 確定已選取根資料夾HKEY_USERS。
       
5. 按一下 [檔案]，然後選擇 [ **載入Hive]。**
6. 流覽至 **C：\Users\Skype** 資料夾，然後在 [檔案名] 方塊中輸入 NTUSER.dat，然後按開啟按鈕

7. 系統會提示您為剛載入的Hivee輸入金鑰名稱;輸入Skype (您現在應該會看到Skype使用者) 的登錄設定。
 
8. 開啟Skype鍵並流覽以HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings然後確定已輸入這些設定： 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    如果 ProxyServer 不存在，您可能需要將此金鑰新增為字串，請將 xx.xx.xx.xx.xx：8080 變更為 Proxy 伺服器的 ip/host 和埠。
 
    如果客戶使用 PAC 檔案，設定看起來會類似下列範例：

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. 完成變更後，請醒目提示 Skype 使用者金鑰 (根資料夾，以供Skype) 使用，然後從 [登錄] 檔案功能表中選擇 [卸載Hive]， (系統會提示您進行確認 - 選取 [**是**) ]。
    
10. 您現在可以關閉登錄編輯程式，並在Windows搜尋方塊中輸入標誌。
    
11. 回到登入畫面，選擇 **Skype** 使用者。 如果上述所有步驟都成功，Microsoft Teams 會議室裝置將會成功登入。
    
如需 FQDN、埠和 IP 位址範圍的完整詳細資料，請參閱[網路安全](./security.md#network-security)性文章，以瞭解Microsoft Teams 會議室所需的詳細資料。
  
### <a name="admin-group-management"></a>系統管理群組管理

如果您加入宣告網域 (Azure Active Directory或 Active Directory) ，您可以使用 Microsoft 端點管理員、群組原則 或本機電腦管理將安全性群組設定為本機系統管理員，就像您在網域中使用Windows電腦一樣。 任何身為該安全性群組成員的人都可以輸入認證並解除鎖定設定。
  
> [!NOTE]
> 例如，如果您的Microsoft Teams 會議室裝置對網域 (失去信任，如果您在網域加入網域後移除網域Microsoft Teams 會議室) ，您將無法驗證裝置並開啟設定。 因應措施是使用本機系統管理員帳戶登入。 
  
## <a name="local-accounts"></a>本機帳戶

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 會議室本機使用者帳戶

Teams 會議室包含名為「Skype」的無密碼本機帳戶。 此帳戶用來登入Windows以啟動 Teams 會議室 應用程式。 不支援將密碼套用至此帳戶。 如[需詳細資訊，](security.md)請參閱Microsoft Teams 會議室安全性]。
  
### <a name="admin---local-administrator-account"></a>「系統管理員」 - 本機系統管理員帳戶

Microsoft Teams 會議室預設密碼設為 「sfb」。 您可以透過本機系統管理員模式或在AutoUnattend.xml檔案中變更密碼 (使用 ADK 的 Windows System Image manager 來變更 xml 檔案) 。
  
> [!CAUTION]
> 請務必儘快變更Microsoft Teams 會議室密碼。 
  
在安裝期間，本機系統管理員密碼不會包含在選項中。

您可以在Microsoft Teams 會議室[安全](security.md)性一文中深入瞭解系統管理員帳戶。
  
### <a name="machine-account"></a>電腦帳戶

就像任何Windows裝置一樣，您可以在 [**關於** \> **重新** 命名電腦] 中以滑鼠右鍵按一下 **滑鼠** 右鍵，重新命名設定 \> 電腦名稱稱。
  
如果您想要在加入網域後重新命名電腦，請使用 [Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2)，一個 PowerShell 命令，後面接著電腦的新名稱。
  
## <a name="related-topics"></a>相關主題

[規劃Microsoft Teams 會議室](rooms-plan.md)

[Microsoft Teams 會議室需求](requirements.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)

[商務用 Microsoft Store和教育的先決條件](/microsoft-store/prerequisites-microsoft-store-for-business)
