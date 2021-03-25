---
title: 設定 Microsoft Teams 會議室主控台
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文將說明如何設定及設定 Microsoft Teams 會議室主控台及其周邊設備。
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117571"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>設定 Microsoft Teams 會議室主控台

本文將說明如何設定 Microsoft Teams 會議室主控台及其周邊設備。
  
只有在已建立並測試必要的 Microsoft Teams 或商務用 Skype 和 Exchange 帳戶時，您才應執行這些步驟，如部署 [Microsoft Teams 會議室中所述](rooms-deploy.md)。 您需要 Microsoft Teams 會議室需求中所述 [的硬體和軟體](requirements.md)。 本主題包含下列各節：
  
- [準備安裝媒體](console.md#Prep_Media)
- [在主機上安裝私人 CA 憑證](console.md#Certs)
- [安裝 Windows 10 和 Microsoft Teams 會議室主控台應用程式](console.md#Reimage)
- [主機的初始設定](console.md#Initial)
- [Microsoft Teams 會議室部署檢查清單](console.md#Checklist)

> [!NOTE]
> Microsoft Teams 會議室只能在正確配置的 Microsoft Teams 或商務用 Skype 環境中運作，其中裝置帳戶已正確設定，如部署 [Microsoft Teams 會議室中所述](rooms-deploy.md)。
  
## <a name="prepare-the-installation-media"></a>準備安裝媒體
<a name="Prep_Media"> </a>

安裝 Microsoft Teams 會議室主控台應用程式需要至少 32 GB 容量的 USB 儲存裝置。 裝置上不應有其他檔案;USB 儲存空間上的任何現有檔案都會遺失。
  
> [!NOTE]
> 如果無法依照這些指示建立您的 Microsoft Teams 會議室安裝媒體，可能會導致意外的行為。

> [!NOTE]
> 以下程式是建立安裝媒體來映射新的 Microsoft Teams 會議室裝置。 根據預設，現有的裝置會從 Windows Update 和 Windows Store 自動更新。

> [!IMPORTANT]
> 用來建立 Microsoft Teams 會議室安裝媒體的 Windows 10 電腦必須與目標安裝媒體位於相同或更新版本的 Windows 上。
  
1. 下載CreateSrsMedia.ps1 [ 腳本](https://go.microsoft.com/fwlink/?linkid=867842)。
2. 在 Windows 10 CreateSrsMedia.ps1上從提升的提示執行此腳本。
3. 按照腳本的指示建立 Microsoft Teams 會議室 USB 設定磁片。


> [!TIP]
> 每一次CreateSrsMedia.ps1腳本啟動時，畫面輸出會包含記錄檔案或會話記錄的名稱。 如果執行腳本時發生問題，請務必在要求支援時提供該腳本的一份副本。 

腳本CreateSrsMedia.ps1自動化下列工作：

1. 下載 Microsoft Teams 會議室的最新 MSI 安裝程式。
2. 決定使用者必須提供的 Windows 版本。 最近發行的版本可能會受到測試，也可能不支援與 Microsoft Teams 會議室裝置一起使用。
3. 下載必要的支援元件。
4. 在安裝媒體上組合所需的元件。

需要特定的 Windows 10 版本，且此版本僅適用于大量授權客戶。  您可以從大量授權服務中心 [取得副本](https://www.microsoft.com/Licensing/servicecenter/)。

完成後，請從電腦移除 USB 磁片，然後繼續安裝 [Windows 10 和 Microsoft Teams 會議室主控台應用程式](console.md#Reimage)。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>安裝 Windows 10 和 Microsoft Teams 會議室主控台應用程式
<a name="Reimage"> </a>

您現在必須申請您建立安裝程式的媒體。 目標裝置會以裝置執行，而預設使用者會設定為只執行 Microsoft Teams 會議室主控台應用程式。

1. 如果目標裝置會安裝在固定 (例如 Surface Pro) ，請將其從固定座中斷連接。

2. 確定目標裝置未連接至網路。

3. 確定目標裝置已連接到 AC 電源。

4. 將 USB 設定磁片插入目標裝置。

5. 啟動至 USB 設定磁片。 請參閱製造商指示。 如果您的目標裝置是 Surface Pro，請使用下列步驟引導至 USB 設定磁片：

    a. 按並繼續按住 (-) 音量。

    b. 按並放開電源按鈕。

    C。 啟動 Windows 安裝程式後，請放開音量 (-) 按鈕。

8. 安裝完成後，系統將會關閉。
    
系統關機後，可以安全地移除 USB 設定磁片。 此時，您可以使用固定式產品 (，將目標裝置放在其固定位置) 附加會議室所需的周邊設備，然後連接至網路。 請參閱製造商指示。

> [!NOTE]
> Microsoft Teams 會議室的軟體更新會自動從商務用 Microsoft Store 下載。 請參閱 [商務用和教育用 Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business) 的先決條件，以確認會議室主控台能夠存取該商店並自我更新。  

### <a name="selecting-a-language"></a>選取語言 

在 Creator 的 Update 中，您必須在隱含語言選擇未提供使用者想要的實際應用程式語言的情況下使用 ApplyCurrentRegionAndLanguage.ps1 腳本 (例如，他們想要以法文顯示主控台應用程式，但即將以英文) 。
  
> [!NOTE]
> 下列指示僅適用于使用 Windows Creator 更新所建立之主機。 尚未使用媒體與新設定系統進行設定的舊式/市集系統將無法使用這些指示，但也應該不會因為需要手動介入的初始問題而受到影響 (Anniversary Edition 讓您在設定) 中明確挑選您的應用程式語言。
  
### <a name="to-apply-your-desired-language"></a>若要使用您想要的語言

1. 切換到系統管理模式。
    
2. 選取開始功能表。
    
3. 選取齒輪圖示以 **啟動設定應用程式** 。
    
4. 選取 **時間 &amp; 語言**。
    
5. 選取 **地區 &amp; 語言**。
    
6. 選取 **新增語言**。
    
7. 選取要新增的語言。
    
8. 選取您剛剛新加入「語言」清單的語言。
    
9. 選取 **設定為預設值**。
    
10. 針對任何想要移除的語言：
    
    a. 選取要移除的語言。
    
    b. 選取 **移除**。
    
11. 啟動提升的命令提示。
    
12. 執行下列命令： 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. 重新開機系統。
    
您所需的語言現在會適用于 Microsoft Teams 會議室主控台。
## <a name="initial-set-up-of-the-console"></a>主機的初始設定
<a name="Initial"> </a>

安裝 Windows 之後，Microsoft Teams 會議室主控台應用程式將在下次啟動或已選擇 /重新開機選項時，進入其初始設定程式。
  
1. 系統會顯示使用者帳戶畫面。 在會議室帳戶的 (中user@domain) Skype 的登錄位址。
    
2. 輸入會議室帳戶的密碼，然後重新輸入密碼進行驗證。
    
3. 在 「設定網域」下，設定商務用 Skype Server 的 FQDN。 如果商務用 Skype SIP 網域與使用者的 Exchange 網域不同，請在此欄位中輸入 Exchange 網域。
    
4. 按一下 **[下一步**。
    
5. 在 [功能畫面上選取指示的裝置，然後按一下 [ **下一步**> 。 預設為將自動螢幕畫面共用設定為 On，而隱藏會議名稱則設為關閉。 要選取的裝置有：
    
   - 會議用麥克風：此會議室的預設麥克風。
    
   - 會議演講者：會議的預設喇叭。 
    
   - 預設喇叭：用於從 HDMI 輸入音訊的喇叭。
    
     每個專案都有一個下拉式功能表，提供要選取的選項。 您必須針對每個裝置進行選取。
    
6. 按一下 **[完成>**。
    
Microsoft Teams 會議室主控台應用程式應該會立即以上述輸入的認證開始登錄商務用 Skype Server，並且也應該使用這些相同的認證開始與 Exchange 同步處理其日曆。 有關使用主機應用程式的詳細資訊，請參閱 [Microsoft Teams 會議室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Microsoft Teams 會議室仰賴通過認證的主機硬體。 即使正確建立的圖像包含 Microsoft Teams 會議室主控台應用程式，除非偵測到主機硬體，否則不會啟動初始設定程式。 針對 Surface Pro 型解決方案，Surface Pro 必須連接到隨附的固定硬體，以通過此檢查。
  
> [!NOTE]
> 如果觸控式鍵盤不支援符號，某些非英文使用者可能需要在初始設定期間將實體鍵盤連接到主機。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在主機上安裝私人 CA 憑證
<a name="Certs"> </a>

Microsoft Teams 會議室主控台必須信任所連接之伺服器所使用的憑證。 針對 O365，系統會自動執行這項操作，因為這些伺服器是使用公用憑證頒發機構，Windows 10 會自動信任這些憑證授權單位。 如果憑證頒發機構是私人的，例如使用 Active Directory 和 Windows 憑證授權單位進行內部部署，您可以用幾種方法將憑證新增到 Microsoft Teams 會議室主控台：
  
- 您可以將主控台加入 Active Directory，並自動新增所需的憑證，因為憑證頒發機構已發佈至 Active Directory (一般部署選項) 。
    
- 您可以在映射處理之後手動安裝憑證。 執行此操作之前，您必須完成 [主機的初始設定](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>若要手動安裝憑證

1. 將 CA 憑證下載到您的電腦，並將其儲存為"C：\Skype 會議室系統\x64\Scripts\Provisioning\CAcertificate.cer"。
    
2. 將主機放在系統管理模式 (請參閱 [系統管理模式和裝置管理](rooms-operations.md#AdminMode)) 。
    
3. 執行下列命令：
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 網域 (選) 
<a name="Certs"> </a>

您可以將 Microsoft Teams 會議室主機加入您的網域。 Microsoft Teams 會議室主機應置於與電腦工作站不同的 OU 中，因為許多工作站策略與 Microsoft Teams 會議室不相容。 常見的範例是密碼強制執行政策，可防止 Microsoft Teams 會議室自動啟動。 如需 GPO 設定管理的資訊，請參閱 [管理 Microsoft Teams 會議室](rooms-operations.md)。
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>若要將 Microsoft Teams 會議室加入網域

1. 從系統管理員帳戶登錄主機 (請參閱系統管理 [模式](rooms-operations.md#AdminMode)) 。
    
2. 啟動提升的 Powershell 命令提示。
    
3. 在 Powershell 中輸入下列命令：
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

例如，如果您的完全合格的網域為 redmond.corp.microsoft.com 且您想要您的 Microsoft Teams 會議室主機位於 「Microsoft Teams 會議室」OU 中，且該 OU 為 「資源」OU 的子級，則命令為：
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果您想要在將電腦加入網域時重新命名，請使用 -NewName 標號，後面接著電腦的新名稱。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams 會議室部署檢查清單
<a name="Checklist"> </a>

使用下列檢查清單，同時進行主機及其所有周邊設備已完全配置的驗證：
  
**應用程式設定**

|||
|:-----|:-----|
|☐  <br/> |會議室帳戶名稱和電話 # (PSTN 啟用) 主機畫面右上方正確顯示  <br/> |
|☐  <br/> |Windows 電腦名稱稱已正確設定 (遠端系統管理)   <br/> |
|☐  <br/> |系統管理員帳戶密碼設定及驗證  <br/> |
|☐  <br/> |已應用所有固件更新  <br/> |
   
**音訊/視音訊周邊**

|||
|:-----|:-----|
|☐  <br/> |若適用，相機外 (固件版本正確)   <br/> |
|☐  <br/> |相機功能與位置最佳  <br/> |
|☐  <br/> |播放預設裝置和播放預設通訊裝置設定為預定的音訊周邊裝置  <br/> |
|☐  <br/> |錄製預設通訊裝置設定為預定的音訊周邊裝置  <br/> |
|☐  <br/> |音訊周邊固件版本正確無誤 (適用)   <br/> |
|☐  <br/> |音訊輸入裝置可運作且位置最佳  <br/> |
|☐  <br/> |音訊輸出裝置可運作且位置最佳  <br/> |
   
**碼頭**

|||
|:-----|:-----|
|☐  <br/> |纜線安全且不會捏合  <br/> |
|☐  <br/> |HDMI 上的音訊輸入功能  <br/> |
|☐  <br/> |在 HDMI 上輸入視像功能  <br/> |
|☐  <br/> |Dock 可以自由旋轉  <br/> |
|☐  <br/> |環境可接受顯示亮度  <br/> |
   
## <a name="see-also"></a>另請參閱
<a name="Checklist"> </a>

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)