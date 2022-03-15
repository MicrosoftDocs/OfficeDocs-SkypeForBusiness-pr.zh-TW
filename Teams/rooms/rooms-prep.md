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
description: 瞭解如何準備基礎結構以部署Microsoft Teams 會議室，以便利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5203972feee8276d9d63c19f65965f62386ee7a0
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503950"
---
# <a name="prepare-your-environment"></a>準備您的環境

本節包含準備環境所需的步驟概觀，以便您可以使用所有Microsoft Teams 會議室。
  
1. 準備每個主機的資源Microsoft Teams 會議室帳戶。 請參閱[部署Microsoft Teams 會議室](rooms-deploy.md)以尋找詳細資料。
    
2. 請確保裝置有可使用的網路/網際網路連接。
  
3. 為了改善您的體驗，Microsoft 會收集資料。 若要允許 Microsoft 收集資料，請允許這些網站：

   - 遙測用戶端端點： https://vortex.data.microsoft.com/
   - 遙測設定端點： https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-resource-account"></a>建立和測試資源帳戶

資源 *帳戶* 是用戶端用來從 Microsoft Teams 會議室 存取功能的帳戶Exchange例如日曆，以及用來Microsoft Teams。 請參閱[部署Microsoft Teams 會議室](rooms-deploy.md)以尋找詳細資料。
  
### <a name="check-network-availability"></a>檢查網路可用性

若要正常運作，Microsoft Teams 會議室必須能存取符合這些要求的有線網路：
  
- 存取 Active Directory 或 Azure Active Directory (Azure AD) 實例，以及 Microsoft Exchange Microsoft Teams。

- 存取可以使用 DHCP 提供 IP 位址的伺服器。 Microsoft Teams 會議室第一次裝置啟動時，無法使用靜態 IP 位址來進行配置。

- 存取 HTTP 埠 80 和 443。

- 根據內部部署 商務用 Skype Server 實現或 Microsoft 365 和 Office 365 URL [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)與[IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)位址範圍之內部部署 商務用 Skype Server 的埠和通訊協定需求所述，針對 Microsoft Teams 所配置的 TCP 和 UDP 埠。

如果您的網路是透過 Proxy 執行，您也需要 Proxy 位址或腳本資訊。
    
> [!IMPORTANT]
> Microsoft Teams 會議室不支援 Proxy 驗證，因為它可能會干擾會議室的一般作業。 在投入Microsoft Teams 會議室之前，請確保已免除 Proxy 驗證。

> [!IMPORTANT]
> 請務必使用有線 1Gbps 網路連接，以確保您擁有所需的頻寬。

> [!NOTE]
> 系統會自動從 Microsoft Teams 會議室 下載適用于 商務用 Microsoft Store。 請參閱[商務用 Microsoft Store與教育](/microsoft-store/prerequisites-microsoft-store-for-business)的先決條件，以確認會議室主控台能夠存取市/市及自我更新。
  
### <a name="certificates"></a>證書

您的Microsoft Teams 會議室裝置會使用憑證Exchange Web Services、Microsoft Teams或商務用 Skype、網路使用方式和驗證。 如果相關伺服器使用公用憑證 ，例如線上和部分內部部署，則系統管理員無需執行其他動作來安裝憑證。 另一方面，如果憑證頒發機構是私人 CA，則裝置必須信任該 CA。 這表示裝置上已安裝 CA + CA 鏈證書。 將裝置新加入網域可能會自動執行這項工作。
  
您安裝憑證的方式，與安裝任何其他用戶端Windows相同。 
  
> [!NOTE]
> 您可能需要憑證才能Microsoft Teams 會議室使用商務用 Skype Server。
  
### <a name="proxy"></a>代理

Microsoft Teams 會議室是從作業系統繼承 Proxy Windows設定。 以下列Windows存取作業系統：
  
1. 在 Microsoft Teams 會議室 UI 中，按一下 設定 齒輪圖示，系統會提示您輸入裝置上的當地系統管理員密碼 (預設密碼為 **sfb**) 。
2. 點 **選 設定**，然後點選前往 **Windows** 按鈕，然後點選前往系統管理登錄按鈕，然後按一下管理員按鈕 (如果電腦已加入網域，請選擇其他使用者，然後使用 .\admin 做為使用者名稱) 。****
3. 在 [**搜尋Windows** 方塊左下輸入 regedit (長按螢幕或以滑鼠右鍵按一下，然後選擇 [以系統管理員) 。****
4. 按一下 [HKEY_USERS資料夾 (，您就會看到電腦使用者 SID 清單，) 已選取HKEY_USERS資料夾。
       
5. 按一下 [檔案>，然後選擇 [ **載入配置單元。**
6. 流覽至 **C：\Users\Skype** 資料夾，然後輸入 NTUSER.dat 的檔案名方塊，然後按開啟按鈕

7. 系統會提示您為新載入的 Hive 輸入 Key Name;輸入Skype (，您現在應該會看到使用者帳戶的登錄Skype) 。
 
8. 開啟Skype鍵並流覽至HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings，然後確保已輸入這些設定： 
    
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
    
9. 一旦完成變更，請為 Skype) 的 Skype 使用者金鑰 (根資料夾加亮，然後選擇從登錄檔案功能表卸載 Hive (系統會提示您確認 - 選取 **是) 。**
    
10. 現在，您可以關閉登錄編輯器，然後輸入登入 Windows方塊。
    
11. 回到登錄畫面，選擇 **Skype使用者。** 如果上述所有步驟都成功，Microsoft Teams 會議室裝置會順利登錄。
    
請參閱[網路安全性](./security.md#network-security)文章，以進一步瞭解 FQDNs、埠和 IP 位址範圍Microsoft Teams 會議室。
  
### <a name="admin-group-management"></a>系統管理群組管理

如果您加入宣告網域 (Azure Active Directory 或 Active Directory) ，您可以使用 Microsoft 端點管理員、群組原則或本地電腦管理將安全性群組設定為本地系統管理員，就像在網域的 Windows 電腦上一樣。 任何加入該安全性群組的人都可以輸入其認證並解除鎖定設定。
  
> [!NOTE]
> 如果您的 Microsoft Teams 會議室 裝置與網域 (失去信任，例如，如果您在網域加入) 之後，從網域移除 Microsoft Teams 會議室，您將無法驗證至裝置並開啟 設定。 解決方法是使用本地系統管理員帳戶登入。 
  
## <a name="local-accounts"></a>本地帳戶

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 會議室使用者帳戶

Teams 會議室包含名為「Skype」的無密碼Skype。 這個帳戶是用來用來Windows應用程式Teams 會議室應用程式。 不支援將密碼用於此帳戶。 請參閱[Microsoft Teams 會議室安全性](security.md)以瞭解更多資訊。
  
### <a name="admin---local-administrator-account"></a>「系統管理員」- 本地系統管理員帳戶

Microsoft Teams 會議室預設密碼設為「sfb」。 透過系統管理模式或在 AutoUnattend.xml 檔案中變更密碼 (請使用 ADK 的 Windows System Image manager 變更 xml 檔案) 。
  
> [!CAUTION]
> 請務必儘快變更Microsoft Teams 會議室密碼。 
  
在設定期間，系統不會提供本地系統管理員密碼做為選項。

You can read more about the Admin account in the [Microsoft Teams Rooms Security](security.md) article.
  
### <a name="machine-account"></a>電腦帳戶

就像任何Windows一樣 \> ，機器名稱可以在關於重新命名電腦設定 **中** \> **以滑鼠右鍵重新命名**。
  
如果您想要在將電腦加入網域後重新命名，請使用 [重新命名-電腦](/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2)，即 PowerShell 命令，後面接著電腦的新名稱。
  
## <a name="related-topics"></a>相關主題

[規劃Microsoft Teams 會議室](rooms-plan.md)

[Microsoft Teams 會議室需求](requirements.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)

[教育與商務用 Microsoft Store的先決條件](/microsoft-store/prerequisites-microsoft-store-for-business)
