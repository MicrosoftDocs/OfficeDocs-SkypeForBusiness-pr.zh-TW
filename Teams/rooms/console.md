---
title: 建立Microsoft Teams 會議室圖像
ms.author: czawideh
author: cazawideh
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文將說明如何設定及設定Microsoft Teams 會議室主機及其周邊裝置。
ms.openlocfilehash: 9c1358b5e9561f197dc1142c40144646b5a11ce4
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676385"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>建立Microsoft Teams 會議室圖像

本文說明如何建立大量部署Teams 會議室的Microsoft Teams 會議室映射。

> [!NOTE]
> 下列步驟僅適用于為大量部署建立 [WIM 影像](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) 。 如果您正在復原個別裝置，請連絡原始設備製造商 (OEM) 尋求支援。

只有在必要Microsoft Teams或商務用 Skype，且Exchange帳戶已如部署Microsoft Teams 會議室中所述建立和測試時[，](rooms-deploy.md)您才應該執行這些步驟。 您需要Microsoft Teams 會議室[需求](requirements.md)中所述的硬體和軟體。 本主題包含下列各節：
  
- [準備安裝媒體](console.md#Prep_Media)
- [在主機上安裝私人 CA 憑證](console.md#Certs)
- [安裝 Windows 10 和 Microsoft Teams 會議室 主機應用程式](console.md#Reimage)
- [主機的初始設定](console.md#Initial)
- [Microsoft Teams 會議室部署檢查清單](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>準備安裝媒體
<a name="Prep_Media"> </a>

安裝Microsoft Teams 會議室主機應用程式需要容量至少為 32 GB 的 USB 儲存裝置。 裝置上應該沒有其他檔案;USB 儲存空間上的任何現有檔案都會遺失。
  
> [!NOTE]
> 無法根據這些指示建立Microsoft Teams 會議室安裝媒體，可能會導致非預期的行為。

> [!NOTE]
> 下列程式是建立安裝媒體來映射新Microsoft Teams 會議室裝置。 根據預設，現有裝置會自動從 Windows Update 和Windows Microsoft Store更新。

> [!IMPORTANT]
> 用來建立Microsoft Teams 會議室安裝媒體的Windows 10電腦必須與目標安裝媒體的Windows版本相同或更新版本。
  
1. 下載 [CreateSrsMedia.ps1腳本](https://go.microsoft.com/fwlink/?linkid=867842)。
2. 從Windows 10電腦上提升許可權的提示執行CreateSrsMedia.ps1腳本。
3. 依照腳本的指示建立Microsoft Teams 會議室 USB 安裝磁片。


> [!TIP]
> 每次CreateSrsMedia.ps1腳本啟動時，螢幕輸出會包含會話記錄檔或文字記錄的名稱。 如果執行腳本時發生問題，請務必在要求支援時取得該文字記錄的複本。 

CreateSrsMedia.ps1腳本會自動化下列工作：

1. 下載適用于 Microsoft Teams 會議室 的最新 MSI 安裝程式。
2. 決定使用者必須提供之Windows的組建。 最新發行的版本可能經過測試，且不支援搭配Microsoft Teams 會議室裝置使用。
3. 下載必要的支援元件。
4. 在安裝媒體上組合所需的元件。

> [!NOTE]
需要特定版本的Windows 10，且此版本僅適用于大量授權客戶。  您可以從 [大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/)取得複本。

完成後，從您的電腦移除 USB 磁片，然後繼續[安裝Windows 10和Microsoft Teams 會議室主機應用程式](console.md#Reimage)。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>安裝 Windows 10 和 Microsoft Teams 會議室 主機應用程式
<a name="Reimage"> </a>

您現在需要套用您已建立的設定媒體。 目標裝置會以設備的形式執行，預設使用者會設為只執行Microsoft Teams 會議室應用程式。

1. 如果目標裝置安裝在擴充座 (例如Surface Pro) ，請將它從擴充座拔除。

2. 確定目標裝置未連線到網路。

3. 確定目標裝置已連接到 AC 電源。

4. 將 USB 安裝程式磁片插入目標裝置。

5. 開機至 USB 安裝程式磁片。 請參閱製造商的指示。 如果您的目標裝置是Surface Pro，請使用下列步驟來開機到 USB 安裝磁片：

    a. 按住並繼續按住降低音量 () 按鈕。

    b. 按下再放開電源按鈕。

    C。 Windows設定開機後，放開音量降低 () 按鈕。

8. 安裝完成後，系統就會關機。
    
系統關機之後，可以放心移除 USB 安裝磁片。 此時，如果使用擴充座型產品) ，您可以將目標裝置置於其擴充座 (、連接會議室所需的周邊裝置，以及連線至網路。 請參閱製造商的指示。

> [!NOTE]
> 系統會自動從商務用 Microsoft Store下載Microsoft Teams 會議室軟體更新。 請參閱[商務用 Microsoft Store和教育版的先決條件](/microsoft-store/prerequisites-microsoft-store-for-business)，以確認會議室主機是否能存取商店並自行更新。  

### <a name="selecting-a-language"></a>選取語言 

在 Creator's Update 中，您將需要使用ApplyCurrentRegionAndLanguage.ps1腳本，以便在隱含語言選取範圍無法提供使用者所需的實際應用程式語言 (，例如，他們想要主機應用程式以法文顯示，但會以英文) 。
  
> [!NOTE]
> 下列指示僅適用于使用 Windows Creator's Update (Windows 10 20H1) 或更新版本建立的主機。
  
### <a name="to-apply-your-desired-language"></a>套用您想要的語言

1. 切換到管理員模式。
    
2. 選取[開始] 功能表。
    
3. 選取齒輪圖示以啟動 **設定** 應用程式。
    
4. 選取 **[時間 &amp; ] 語言**。
    
5. 選取 **語言**。
    
6. 選 **取 [新增語言]**。
    
7. 選取您要新增的語言。
    
8. 安裝語言功能。
    
9. 請勿核取 [設為我的Windows顯示語言]。
    
10. 選取 **[安裝]**。
    
11. 選取您剛才新增至 [語言] 清單的語言。
    
12. 設定為預設值- 向上移動箭號以設定預設值

13. 針對您想要移除的任何語言：
    
    a. 選取您要移除的語言。
    
    b. 選取 [移除]。

14. 啟動提升許可權的命令提示字元。

15. 執行下列命令： 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. 重新開機系統。
    
您想要的語言現在會套用到Microsoft Teams 會議室主機。
## <a name="initial-set-up-of-the-console"></a>主機的初始設定
<a name="Initial"> </a>

安裝Windows之後，Microsoft Teams 會議室應用程式將會進入其初始設定程式。
  
1. [使用者帳戶] 畫面隨即出現。 輸入 Microsoft Exchange Resource 帳戶登入位址 (user@domain格式) 要搭配主機使用的聊天室帳戶。
    
2. 輸入聊天室帳戶的密碼，然後重新輸入以進行驗證。
   
3. 選取支援的會議模式 - Microsoft Teams僅限商務用 Skype，或兩個混合模式選項的其中之一。 如有需要，請啟用新式驗證。

4. 選取 **[下一步]**。
    
5. 如果使用 商務用 Skype，且商務用 Skype SIP 網域與使用者的Exchange網域不同，請在 [進階] 區段中設定商務用 Skype Server的 FQDN。 如果您使用的不是 商務用 Skype 或 SIP 網域符合Exchange網域，請將本節留白。
6. 選取 **[下一步]**。
    
7. 選取 [ **完成]**。
    
Microsoft Teams 會議室應用程式應該使用上述輸入的認證登入Microsoft Teams或商務用 Skype Server，並且應該開始使用相同的認證來同步處理行事曆與Exchange。 如需使用Teams 會議室的詳細資訊，請參閱[Microsoft Teams 會議室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Microsoft Teams 會議室仰賴通過認證的主機硬體。 即使已正確建立且包含Microsoft Teams 會議室主機應用程式的影像，除非偵測到主機硬體，否則不會開機通過初始設定程式。 針對Surface Pro型解決方案，Surface Pro必須連線至其隨附的擴充座硬體，才能通過此檢查。
  
> [!NOTE]
> 在初始設定期間，某些非英文語言的使用者可能需要將實體鍵盤連接到主機，以防觸控式鍵盤不支援符號。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在主機上安裝私人 CA 憑證
<a name="Certs"> </a>
> [!NOTE]
> 下列情況僅適用于將 Teams 會議室 連線至 商務用 Skype。

Microsoft Teams 會議室必須信任所連線伺服器所使用的憑證。 如果憑證頒發機構單位是私人的，例如使用 Active Directory 和 Windows 憑證授權單位單位的內部部署，您可以透過幾種方式將憑證新增至Microsoft Teams 會議室：
  
- 您可以將主機加入 Active Directory，並自動將憑證授權單位單位的必要憑證發佈到 Active Directory (一般部署選項) 。
    
- 您可以在進行影像處理常式後手動安裝憑證。 執行此動作之前，您必須先完成 [主機的初始設定](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>手動安裝憑證

1. 將 CA 憑證下載到您的電腦，並儲存至「C：\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer」。
    
2. 將主機置於系統管理模式 (請參[閱管理員模式和裝置管理](rooms-operations.md#AdminMode)) 。
    
3. 執行下列命令：
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 網域 (選用) 
<a name="Certs"> </a>

您可以加入Microsoft Teams 會議室至您的網域。 Microsoft Teams 會議室應該放在電腦工作站的個別 OU 中，因為許多工作站原則與Microsoft Teams 會議室不相容。 一個常見的範例是密碼強制執行原則，可防止Microsoft Teams 會議室自動啟動。 如需 GPO 設定管理的相關資訊，請參閱[管理Microsoft Teams 會議室](rooms-operations.md)。
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>若要加入網域Microsoft Teams 會議室

1. 從系統管理員帳戶登入主機 (請參[閱管理員模式和裝置管理](rooms-operations.md#AdminMode)) 。
    
2. 啟動提升許可權的 Powershell 命令提示字元。
    
3. 在 Powershell 中輸入下列命令：
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

例如，如果您的完整網域 redmond.corp.microsoft.com，而您希望您的Microsoft Teams 會議室主機處於「Microsoft Teams 會議室」OU 中，而該網域是「Resources」OU 的子系，則命令會是：
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果您想要在將電腦加入網域時重新命名，請使用 -NewName 標幟，後面接著電腦的新名稱。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams 會議室部署檢查清單
<a name="Checklist"> </a>

執行主機及其所有周邊裝置已完全設定的最終驗證時，請使用下列檢查清單：
  
**應用程式設定**

|完成 |檢查 |
|:-----:|:-----|
|☐   |會議室帳戶名稱和手機 # (啟用 PSTN 時，) 正確顯示   |
|☐   |Windows電腦名稱稱設定正確 (適用于遠端系統管理)    |
|☐   |系統管理員帳戶密碼設定和驗證   |
|☐   |已套用所有韌體更新   |
   
**音訊/視訊周邊設備**

|完成 |檢查 |
|:-----:|:-----|
|☐   |相機介面韌體版本在適用 ()    |
|☐   |相機功能和位置優化   |
|☐   |[播放預設裝置] 和 [播放預設通訊裝置] 設定為預定音訊周邊裝置的設定   |
|☐   |錄製預設通訊裝置的設定設定為預定的音訊周邊設備   |
|☐   |如果適用的話，音訊周邊韌體版本 (正確)    |
|☐   |音訊輸入裝置可運作且位置最佳   |
|☐   |音訊輸出裝置運作正常且位置最佳   |

**主控台**

|完成 |檢查 |
|:-----:|:-----|
|☐   |纜線安全無捏合   |
|☐   |透過 HDMI的音訊功能   |
|☐   |透過 HDMI 塞入視訊功能   |
|☐   |主機可以自由旋轉   |



   
## <a name="see-also"></a>另請參閱
<a name="Checklist"> </a>

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
