---
title: 準備您的環境
ms.author: dstrome
author: dstrome
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
description: 瞭解如何準備基礎結構以部署 Microsoft Teams 會議室，以便利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117421"
---
# <a name="prepare-your-environment"></a>準備您的環境

本節包含準備環境所需的步驟概觀，以便您可以使用 Microsoft Teams 會議室的所有功能。
  
1. 準備每個 Microsoft Teams 會議室主控台的裝置帳戶。 請參閱 [部署 Microsoft Teams 會議室](rooms-deploy.md) 以瞭解詳細資料。
    
2. 請確保裝置有可使用的網路/網際網路連接。 
    
   它必須能夠使用 DHCP 接收 IP 位址。  (第一次裝置啟動時，Microsoft Teams 會議室無法以靜態 IP 位址進行配置，但之後，裝置上的靜態 IP 位址可以在裝置上或上行交換器或路由器上) 

   除了開啟媒體的一般 (之外，還必須開啟這些埠) ：
   - HTTPS：443
   - HTTP：80

   如果您的網路是透過 Proxy 執行，您也需要 Proxy 位址或腳本資訊。
    
   > [!IMPORTANT]
   > Microsoft Teams 會議室不支援 Proxy 驗證，因為它可能會干擾聊天室的一般作業。 在投入生產之前，請確保 Microsoft Teams 會議室已免于 Proxy 驗證。
  
3. 為了改善您的體驗，Microsoft 會收集資料。 若要允許 Microsoft 收集資料，請允許這些網站：

   - 遙測用戶端端點： https://vortex.data.microsoft.com/
   - 遙測設定端點： https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>建立和測試裝置帳戶

裝置  *帳戶*  是 Microsoft Teams 會議室用戶端用來從 Exchange 存取功能的帳戶，例如日曆，以及啟用商務用 Skype。 請參閱 [部署 Microsoft Teams 會議室](rooms-deploy.md) 以瞭解詳細資料。
  
### <a name="check-network-availability"></a>檢查網路可用性

若要正常運作，Microsoft Teams 會議室裝置必須能夠存取符合這些要求的有線網路：
  
- 存取 Active Directory 或 Azure Active Directory (Azure AD) 實例，以及您的 Microsoft Exchange 和商務用 Skype 伺服器。

- 存取可以使用 DHCP 提供 IP 位址的伺服器。 Microsoft Teams 會議室無法在第一次裝置啟動時以靜態 IP 位址進行配置。

- 存取 HTTP 埠 80 和 443。

- 針對內部部署商務用 Skype Server[](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)的部署，或 Microsoft Teams 或商務用 Skype 線上實現之[Microsoft 365 和 Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) URL 和 IP 位址範圍的伺服器埠和通訊協定需求中所述，所配置的 TCP 和 UDP 埠。

> [!IMPORTANT]
> 請務必使用有線 1Gbps 網路連接，以確保您擁有所需的頻寬。

> [!NOTE]
> Microsoft Teams 會議室的軟體更新會自動從商務用 Microsoft Store 下載。 請參閱 [商務用和教育用 Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business) 的先決條件，以確認會議室主控台能夠存取該商店並自我更新。
  
### <a name="certificates"></a>證書

您的 Microsoft Teams 會議室裝置會使用 Exchange Web Services、Microsoft Teams 或商務用 Skype、網路使用方式和驗證的憑證。 如果相關伺服器使用公用憑證 ，例如 Online 和部分內部部署，則系統管理員無需執行其他動作來安裝憑證。 另一方面，如果憑證頒發機構是私人 CA (通常是內部部署) 則裝置必須信任該 CA，這表示裝置上安裝 CA + CA 鏈證書。 將裝置新加入網域可能會自動執行這項工作。
  
您安裝憑證的方式，與任何其他 Windows 用戶端相同。 
  
> [!NOTE]
> 若要讓 Microsoft Teams 會議室使用商務用 Skype Server，可能需要憑證。
  
### <a name="proxy"></a>代理

Microsoft Teams 會議室是設計用來繼承 Windows OS 的 Proxy 設定。 以下列方式存取 Windows 作業系統：
  
1. 在 Microsoft Teams 會議室 UI 中，按一下 [設定> 齒輪圖示，系統會提示您輸入裝置上的當地系統管理員密碼 (預設密碼為 **sfb**) 。
2. 點選 **設定**，然後點選前往 **Windows** 按鈕，然後點選前往管理員登錄按鈕，然後按一下管理員按鈕 (如果電腦已加入網域，請選擇其他使用者，然後使用 .\admin 做為使用者名稱) 。 
3. 在 regedit 中的 [**搜尋 Windows** (方塊中，長按螢幕或以滑鼠右鍵按一下，然後選擇 [以系統管理員) 。
4. 按一下 [HKEY_USERS資料夾 (，就會看到電腦使用者 SID 清單，) 已選取HKEY_USERS資料夾。
       
5. 按一下 [檔案>，然後選擇 [ **載入配置單元。**
6. 流覽至 **C：\Users\Skype** 資料夾，然後輸入檔案名方塊 NTUSER.dat，然後按開啟按鈕

7. 系統會提示您為新載入的 Hive 輸入 Key Name;輸入 Skype (現在您應該會看到 Skype 使用者帳戶的登錄) 。
 
8. 開啟 Skype 鍵並流覽至HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings，然後確保已輸入這些設定： 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    如果 ProxyServer 不存在，您可能需要將此金鑰新增為字串，將 xx.xx.xx.xx：8080 變更為 Proxy 伺服器的 ip/host 和埠。
 
    如果客戶使用 PAC 檔案，該組組看起來會類似下列範例：

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. 一旦完成變更，請針對 Skype) 的 Skype 使用者金鑰 (根資料夾，並選取從登錄檔案功能表卸載 Hive (系統會提示您確認 - 選取是) 。 
    
10. 現在，您可以關閉登錄編輯器，然後輸入登入 Windows 搜尋方塊。
    
11. 回到登錄畫面，選擇 **Skype** 使用者。 如果上述所有步驟都成功，Microsoft Teams 會議室裝置將會順利登錄。
    
請參閱 [網路安全性](./security.md#network-security) 文章，瞭解 Microsoft Teams 會議室所需的 FQDN、埠和 IP 位址範圍的完整詳細資料。
  
  
### <a name="create-provisioning-packages"></a>建立部署套件

您將使用部署套件來驗證 Exchange Server、Microsoft 365 或 Office 365。
  
### <a name="admin-group-management"></a>系統管理群組管理

加入網域之後，您可以使用群組原則或本地電腦管理將安全性組設定為本地系統管理員，就像您網域內 Windows 電腦一樣。 任何加入該安全性群組的人都可以輸入其認證並解除鎖定設定。
  
> [!NOTE]
> 如果您的 Microsoft Teams 會議室裝置失去對網域 (的信任，例如，如果您在加入網域) 後從網域移除 Microsoft Teams 會議室，您將無法驗證至裝置並開啟設定。 解決方法是使用本地系統管理員帳戶登入。 
  
## <a name="local-accounts"></a>本地帳戶

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 會議室本地使用者帳戶

裝置帳戶通常不會使用密碼。 您可以提供密碼，但會產生一些後果，包括使用者可能在密碼到期時被鎖定在主機應用程式外。 因此，系統管理員應該採取一些措施，確保密碼不會過期。
  
### <a name="admin---local-administrator-account"></a>「系統管理員」- 本地系統管理員帳戶

Microsoft Teams 會議室的預設密碼設定為「sfb」。 您可以前往 Windows 設定前往 Windows，或在 AutoUnattend.xml 檔案中變更密碼 (使用 ADK 的 Windows System Image manager 變更 xml 檔案 \>) 。
  
> [!CAUTION]
> 請務必儘快變更 Microsoft Teams 會議室密碼。 
  
您也可以設定群組原則，將網域系統管理員設定為本地系統管理員，以管理本地系統管理員密碼。
  
在設定期間，系統不會提供本地系統管理員密碼做為選項。
  
### <a name="machine-account"></a>電腦帳戶

就像任何 Windows 裝置一樣，以滑鼠右鍵按一下關於重新命名電腦的設定，即可 \>  \> **重新命名電腦名稱稱**。
  
如果您想要在將電腦加入網域後重新命名，請使用 **重新命名-電腦**，即 PowerShell 命令，後面接著電腦的新名稱。
  
## <a name="related-topics"></a>相關主題

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[Microsoft Teams 會議室需求](requirements.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)

[商務與教育用 Microsoft Store 的先決條件](/microsoft-store/prerequisites-microsoft-store-for-business)