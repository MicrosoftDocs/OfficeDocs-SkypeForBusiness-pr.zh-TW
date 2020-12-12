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
description: 本文說明如何設定和設定 Microsoft 團隊聊天室主控台及其外設。
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662058"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>設定 Microsoft Teams 會議室主控台

本文說明如何設定 Microsoft 團隊聊天室主控台及其外設。
  
如果已建立並測試必要的 Microsoft 團隊或商務用 Skype 與 Exchange 帳戶，請依照 [部署 Microsoft 團隊聊天室](rooms-deploy.md)中的說明，只需執行這些步驟。 您將需要 [Microsoft 團隊會議室需求](requirements.md)中所述的硬體和軟體。 本主題包含下列各節：
  
- [準備安裝媒體](console.md#Prep_Media)
- [在主控台上安裝私人 CA 憑證](console.md#Certs)
- [安裝 Windows 10 和 Microsoft 團隊聊天室主控台應用程式](console.md#Reimage)
- [主機的初始設定](console.md#Initial)
- [Microsoft 團隊聊天室部署檢查清單](console.md#Checklist)

> [!NOTE]
> Microsoft 團隊聊天室只能在設定正確的 Microsoft 團隊或商務用 Skype 環境中運作，如 [部署 Microsoft 團隊聊天室](rooms-deploy.md)中所述。
  
## <a name="prepare-the-installation-media"></a>準備安裝媒體
<a name="Prep_Media"> </a>

安裝 Microsoft 團隊聊天室主控台 app 需要至少32GB 容量的 USB 儲存空間。 裝置上不應有任何其他檔案;USB 儲存空間中的任何現有檔案將會遺失。
  
> [!NOTE]
> 無法根據這些指示建立您的 Microsoft 團隊會議室安裝媒體，可能會導致意外的行為。

> [!NOTE]
> 下列程式適用于建立安裝媒體至影像新的 Microsoft 團隊聊天室裝置。 根據預設，現有的裝置會自動從 Windows Update 和 Windows 市集中更新。

> [!IMPORTANT]
> 用來建立 Microsoft 團隊聊天室安裝媒體的 Windows 10 電腦，必須位於與目標安裝媒體相同或更新版本的 Windows 上。
  
1. 下載 [CreateSrsMedia.ps1 腳本](https://go.microsoft.com/fwlink/?linkid=867842)。
2. 從 Windows 10 電腦上的提升提示執行 CreateSrsMedia.ps1 腳本。
3. 遵循腳本的指示來建立 Microsoft 團隊聊天室 USB 安裝盤。


> [!TIP]
> 每次 CreateSrsMedia.ps1 腳本啟動時，畫面輸出都會包含會話的記錄檔案名稱或記錄。 如果執行腳本時發生問題，請務必在要求支援時提供該記錄的複本。 

CreateSrsMedia.ps1 腳本會自動執行下列任務：

1. 下載適用于 Microsoft 團隊聊天室的最新 MSI 安裝程式。
2. 決定使用者必須提供的 Windows 組建。 最近發行的版本可能與或不受測試，而且不支援與 Microsoft 團隊聊天室裝置搭配使用。
3. 下載必要的支援元件。
4. 在安裝媒體上組裝所需的元件。

需要 Windows 10 的特定版本，而且這個版本只提供大量授權客戶。  您可以從 [大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/)取得複本。

完成後，請從您的電腦中移除 USB 磁片，然後繼續 [安裝 Windows 10 和 Microsoft 團隊聊天室主控台 app](console.md#Reimage)。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>安裝 Windows 10 和 Microsoft 團隊聊天室主控台應用程式
<a name="Reimage"> </a>

您現在必須套用您所建立的安裝媒體。 目標裝置將會以裝置的方式執行，而且預設使用者將會設定為只執行 Microsoft 團隊聊天室主控台 app。

1. 如果目標裝置將會安裝在 dock 中 (例如 Surface Pro) ，請將它從 dock 中中斷。

2. 確定目標裝置未連線至網路。

3. 確定目標裝置已連線至交流電源。

4. 將 USB 安裝盤插入目標裝置。

5. 啟動至 USB 安裝盤。 請參閱製造商的指示。 如果您的目標裝置是 Surface Pro，請使用下列步驟引導至 USB 安裝盤：

    a. 按下並持續按住音量， ( ) ] 按鈕。

    b. 按下並放開 [電源] 按鈕。

    c-clip. 啟動 Windows 安裝程式後，請 ( ) ] 按鈕向下釋放音量。

8. 安裝完成後，系統會關閉。
    
系統關閉之後，就可以安全地移除 USB 安裝盤了。 此時，您可以將目標裝置放在其 dock 中 (如果您使用的是 dock 產品) ，請附加會議室所需的外設，然後連線到網路。 請參閱製造商的指示。

> [!NOTE]
> Microsoft 團隊聊天室的軟體更新會自動從商務用 Microsoft 網上商店下載。 請參閱 [Microsoft Store For Business 和教育版的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) ，確認聊天室主機能夠存取商店及自我更新。  

### <a name="selecting-a-language"></a>選取語言 

在建立者的更新中，當隱含語言選取不會提供使用者所需的實際應用程式語言時，您將需要使用 ApplyCurrentRegionAndLanguage.ps1 腳本 (例如，他們想要讓主控台 app 以法文來提出，但它會在英文) 中推出。
  
> [!NOTE]
> 下列指示僅適用于使用 Windows Creator 更新程式建立的主控台。 未使用新的置備系統的媒體進行設定的舊版/內建系統將無法使用這些指示，但也不會受到需要此手動干預的初始問題 (周年紀念版本中，您可以在設定) 中明確挑選您的應用程式語言。
  
### <a name="to-apply-your-desired-language"></a>若要套用您想要的語言

1. 切換到 [管理員模式]。
    
2. 選取 [開始] 功能表。
    
3. 選取齒輪圖示以啟動 [ **設定** ] app。
    
4. 選取 [ **時間 &amp; 語言**]。
    
5. 選取 [ **地區 &amp; 語言**]。
    
6. 選取 [ **新增語言**]。
    
7. 選取您想要新增的語言。
    
8. 選取您剛才新增至 [語言] 清單的語言。
    
9. 選取 [ **設成預設值**]。
    
10. 針對您想要移除的任何語言：
    
    a. 選取您要移除的語言。
    
    b. 選取 [ **移除**]。
    
11. 啟動提升許可權的命令提示字元。
    
12. 執行下列命令： 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. 重新開機系統。
    
您想要的語言現在已套用至 Microsoft 團隊聊天室主控台。
## <a name="initial-set-up-of-the-console"></a>主機的初始設定
<a name="Initial"> </a>

安裝 Windows 之後，當您下一次啟動或選取 [/reboot] 選項時，Microsoft [小組聊天室] 主控台 app 就會進入初始設定處理常式。
  
1. [使用者帳戶] 畫面隨即出現。 在要與主機搭配使用的房間帳戶) 中，輸入 (user@domain 格式的 Skype 登入位址。
    
2. 輸入房間帳戶的密碼，然後重新輸入以進行驗證。
    
3. 在 [設定網域] 底下，設定商務用 Skype Server 的 FQDN。 如果商務用 Skype SIP 網域與使用者的 Exchange 網域不同，請在此欄位中輸入 Exchange 網域。
    
4. 按一下 **[下一步]**。
    
5. 在 [功能] 畫面上選取所指示的裝置，然後按 **[下一步]**。 預設值是將 [自動螢幕共用] 設定為 [開啟]，並隱藏會議名稱設定為 [關閉]。 要選取的裝置包括：
    
   - 會議麥克風：此會議室的預設麥克風。
    
   - 會議的演講者：會議的預設喇叭。 
    
   - 預設喇叭：從 HDMI 接收音訊所用的喇叭。
    
     每個專案都有下拉式清單，其中包含選取的選項。 您必須為每個裝置進行選取。
    
6. 按一下 **[完成]**。
    
Microsoft [團隊聊天室] 主控台 app 應該會立即開始使用上述輸入的認證來登入商務用 Skype Server，也應該使用相同的認證開始與 Exchange 同步處理其行事曆。 如需使用主控台 app 的詳細資料，請參閱 [Microsoft 團隊聊天室](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)說明。
  
> [!IMPORTANT]
> Microsoft 團隊聊天室會依賴已認證的主控台硬體是否存在。 即使有正確建立的包含 Microsoft 團隊聊天室主控台應用程式的影像，也不會超過初始設定程式（除非偵測到主控台硬體），否則不會啟動。 針對 Surface Pro 解決方案，Surface Pro 必須連線至其隨附的 dock 硬體，才能傳送此檢查。
  
> [!NOTE]
> 某些非英文語言的使用者在初始設定期間，可能需要有一個與主機連接的物理鍵盤，在觸控式鍵盤上不支援此符號。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在主控台上安裝私人 CA 憑證
<a name="Certs"> </a>

Microsoft [小組聊天室] 主控台需要信任其所連接之伺服器所使用的憑證。 針對 O365，這會自動完成，因為這些伺服器使用的是公用憑證授權單位，且這些伺服器會自動受 Windows 10 信任。 在憑證授權單位是私人的情況下（例如，內部部署與 Active Directory 和 Windows Certificate 機關），您可以使用下列幾種方式將憑證新增到 Microsoft 團隊聊天室主控台：
  
- 您可以將主機加入 Active Directory，而且會自動將指定給憑證授權單位的必要憑證發佈至 Active Directory (標準部署選項) 。
    
- 您可以在影像處理常式之後，手動安裝證書。 在執行此動作之前，您必須先完成主機 [的初始設定](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>手動安裝憑證

1. 將 CA 憑證下載到您的電腦，並將它儲存到 [C:\Skype 聊天室 Systems\x64\Scripts\Provisioning\CAcertificate.cer]。
    
2. 將主機置於 [管理員模式] (請參閱 [ [管理員模式] 和 [裝置管理]](rooms-operations.md#AdminMode)) 。
    
3. 執行下列命令：
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 網域 (選擇性) 
<a name="Certs"> </a>

您可以將 Microsoft 團隊聊天室主控台加入您的網域。 Microsoft 團隊聊天室主控台應該與電腦工作站放在不同的 OU 中，因為許多工作站原則都不與 Microsoft 團隊聊天室相容。 常見的範例是密碼強制原則，可避免 Microsoft 團隊聊天室自動啟動。 如需管理 GPO 設定的相關資訊，請參閱 [管理 Microsoft 團隊聊天室](rooms-operations.md)。
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>將 Microsoft 團隊聊天室加入網域

1. 從 [管理員帳戶] 登入主機 (請參閱系統 [管理員模式和裝置管理](rooms-operations.md#AdminMode)) 。
    
2. 啟動提升的 Powershell 命令提示字元。
    
3. 在 Powershell 中輸入下列命令：
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

例如，如果您的完整網域是 redmond.corp.microsoft.com，而您想要將 Microsoft 團隊聊天室主控台放在作為「資源」 OU 子級的「Microsoft 球隊聊天室」 OU 中，則此命令將會是：
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果您想要在將電腦加入網域時重新命名，請使用-NewName 標誌，後面接著電腦的新名稱。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft 團隊聊天室部署檢查清單
<a name="Checklist"> </a>

在執行最終驗證時，請使用下列檢查清單，並對所有週邊設備進行完整的設定：
  
**應用程式設定**

|||
|:-----|:-----|
|☐  <br/> |會議室帳戶名稱和電話 # (如果已啟用 PSTN) 在主控台畫面的右上方能正確顯示  <br/> |
|☐  <br/> |Windows 電腦名稱稱設定正確 (適用于遠端系統管理)   <br/> |
|☐  <br/> |已設定並驗證管理員帳戶密碼  <br/> |
|☐  <br/> |已套用所有的固件更新  <br/> |
   
**音訊/視頻外設**

|||
|:-----|:-----|
|☐  <br/> |如果適用的話，相機週邊版固件版本是正確的 ()   <br/> |
|☐  <br/> |相機功能和定位最佳  <br/> |
|☐  <br/> |[播放預設裝置] 和 [播放預設通訊裝置] 設定設為預期音訊外設的設定  <br/> |
|☐  <br/> |錄製預設通訊裝置設定為預期音訊外設的設定  <br/> |
|☐  <br/> |音訊外設固件版本正確 (（如果適用的話）)   <br/> |
|☐  <br/> |音訊輸入裝置功能與最佳位置  <br/> |
|☐  <br/> |音訊輸出裝置功能與最佳位置  <br/> |
   
**進貨**

|||
|:-----|:-----|
|☐  <br/> |纜線安全且無法 pinched  <br/> |
|☐  <br/> |在 HDMI 上的音訊攝取功能正常運作  <br/> |
|☐  <br/> |在 HDMI 上的影片接收功能正常運作  <br/> |
|☐  <br/> |固定塢可自由旋轉  <br/> |
|☐  <br/> |環境可接受顯示器亮度  <br/> |
   
## <a name="see-also"></a>另請參閱
<a name="Checklist"> </a>

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
