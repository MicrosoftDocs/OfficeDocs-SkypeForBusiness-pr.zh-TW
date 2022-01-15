---
title: 建立Microsoft Teams 會議室圖像
ms.author: dstrome
author: dstrome
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
description: 本文將說明如何設定及設定主機Microsoft Teams 會議室及其周邊設備。
ms.openlocfilehash: d6c675ed6eb6f50cf41b817770caf723f75f556b
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055643"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>建立Microsoft Teams 會議室圖像

本文將說明如何建立一個Microsoft Teams 會議室映射，以大量部署Teams 會議室。

> [!NOTE]
> 只有在建立 [WIM](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) 型映射進行大量部署時，才應使用下列步驟。 如果您要復原個別裝置，請與您的原始設備製造商聯繫 (OEM) 以提供支援。

您必須執行這些步驟，Microsoft Teams或商務用 Skype帳戶Exchange已建立和測試 ，如部署 Microsoft Teams 會議室[中所述。](rooms-deploy.md) 您需要上述的硬體和軟體Microsoft Teams 會議室[需求](requirements.md)。 本主題包含下列各節：
  
- [準備安裝媒體](console.md#Prep_Media)
- [在主機上安裝私人 CA 憑證](console.md#Certs)
- [安裝Windows 10主機Microsoft Teams 會議室應用程式](console.md#Reimage)
- [主機的初始設定](console.md#Initial)
- [Microsoft Teams 會議室部署檢查清單](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>準備安裝媒體
<a name="Prep_Media"> </a>

安裝主機Microsoft Teams 會議室需要至少 32 GB 容量的 USB 儲存裝置。 裝置上不應有其他檔案;USB 儲存空間上的任何現有檔案都會遺失。
  
> [!NOTE]
> 如果無法根據這些Microsoft Teams 會議室建立您的安裝媒體，可能會導致意外的行為。

> [!NOTE]
> 下列程式是建立安裝媒體以將新裝置Microsoft Teams 會議室影像。 根據預設，現有的裝置會從 Windows 和 Windows 自動更新。

> [!IMPORTANT]
> 用來Windows 10安裝媒體Microsoft Teams 會議室電腦必須位於與目標安裝媒體相同的或Windows版本。
  
1. 下載CreateSrsMedia.ps1 [ 腳本](https://go.microsoft.com/fwlink/?linkid=867842)。
2. 從CreateSrsMedia.ps1電腦上提升的提示執行Windows 10腳本。
3. 按照腳本的指示建立 USB Microsoft Teams 會議室磁片。


> [!TIP]
> 每次腳本CreateSrsMedia.ps1，畫面輸出會包含記錄檔案或會話記錄的名稱。 如果執行腳本時發生問題，請務必在要求支援時提供該腳本的一份副本。 

腳本CreateSrsMedia.ps1自動化下列工作：

1. 下載最新的 MSI 安裝程式Microsoft Teams 會議室。
2. 決定使用者Windows的建立。 最近發行的版本可能會受到測試，也可能不支援與Microsoft Teams 會議室一起使用。
3. 下載必要的支援元件。
4. 在安裝媒體上組合所需的元件。

> [!NOTE]
需要特定版本的 Windows 10，且此版本僅適用于大量授權客戶。  您可以從大量授權服務中心 [取得副本](https://www.microsoft.com/Licensing/servicecenter/)。

完成後，請從電腦移除 USB 磁片，然後繼續進行安裝 Windows 10 和 Microsoft Teams 會議室[App。](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>安裝Windows 10主機Microsoft Teams 會議室應用程式
<a name="Reimage"> </a>

您現在必須申請您建立安裝程式的媒體。 目標裝置會以裝置執行，而預設使用者會設為只執行Microsoft Teams 會議室應用程式。

1. 如果目標裝置會安裝在固定 (例如，Surface Pro) ，請將其從固定座中斷連接。

2. 確定目標裝置未連接至網路。

3. 確定目標裝置已連接到 AC 電源。

4. 將 USB 設定磁片插入目標裝置。

5. 啟動至 USB 設定磁片。 請參閱製造商指示。 如果您的目標裝置是Surface Pro，請使用下列步驟引導至 USB 設定磁片：

    a. 按並繼續按住 (-) 音量。

    b. 按並放開電源按鈕。

    C。 啟動Windows設定後，請放開音量 () 按鈕。

8. 安裝完成後，系統會關閉。
    
系統關閉之後，可以安全地移除 USB 設定磁片。 此時，您可以使用固定式產品 (，將目標裝置放在其固定位置) 附加會議室所需的周邊設備，然後連接至網路。 請參閱製造商指示。

> [!NOTE]
> 系統會自動從 Microsoft Teams 會議室 下載適用于 商務用 Microsoft Store。 請參閱[商務用 Microsoft Store與教育](/microsoft-store/prerequisites-microsoft-store-for-business)的先決條件，以確認會議室主控台能夠存取市/市及自我更新。  

### <a name="selecting-a-language"></a>選取語言 

在 Creator 的 Update 中，您必須在隱含語言選擇未提供使用者想要的實際應用程式語言的情況下使用 ApplyCurrentRegionAndLanguage.ps1 腳本 (例如，他們想讓主控台應用程式以法文顯示，但會以英文) 提供。
  
> [!NOTE]
> 下列指示僅適用于使用 Creator Windows 20H1 (Windows 10或更新) 的主機。
  
### <a name="to-apply-your-desired-language"></a>若要使用您想要的語言

1. 切換到系統管理模式。
    
2. 選取[開始] 功能表。
    
3. 選取齒輪圖示以 **啟動設定應用程式**。
    
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
    
您所需的語言現在會Microsoft Teams 會議室主控台。
## <a name="initial-set-up-of-the-console"></a>主機的初始設定
<a name="Initial"> </a>

安裝Windows之後，Microsoft Teams 會議室應用程式會進入其初始設定程式。
  
1. 系統會顯示使用者帳戶畫面。 輸入 Microsoft Exchange資源帳戶的登錄 (，user@domain) 會議室帳戶與主機一起使用。
    
2. 輸入會議室帳戶的密碼，然後重新輸入密碼進行驗證。
   
3. 選取支援的會議模式 - Microsoft Teams、商務用 Skype或兩個混合模式選項之一。 如有需要，請啟用新式驗證。

4. 按一下 **[下一步**。
    
5. 如果您使用 商務用 Skype，商務用 Skype SIP 網域與使用者的 Exchange 網域不同，請設定進商務用 Skype Server區段的 FQDN。 如果您不是使用 商務用 Skype SIP 網域與 Exchange網域，請保留此區段空白。
6. 按一下 **[下一步**。
    
7. 按一下 **[完成>**。
    
應用程式Microsoft Teams 會議室使用上述Microsoft Teams商務用 Skype Server來登錄或商務用 Skype Server，並且也應該使用這些相同的認證開始同步處理其Exchange日曆。 有關使用Teams 會議室的詳細資訊，請參閱Microsoft Teams 會議室[說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Microsoft Teams 會議室取決於通過認證的主機硬體。 即使正確建立的圖像包含Microsoft Teams 會議室主機應用程式，除非偵測到主機硬體，否則不會啟動初始設定程式。 針對Surface Pro型解決方案，Surface Pro必須連接到其隨附的固定硬體，以通過此檢查。
  
> [!NOTE]
> 如果觸控式鍵盤不支援符號，某些非英文使用者可能需要在初始設定期間將實體鍵盤連接到主機。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在主機上安裝私人 CA 憑證
<a name="Certs"> </a>
> [!NOTE]
> 只有在將使用者連接到Teams 會議室時，商務用 Skype。

Microsoft Teams 會議室必須信任所連接之伺服器所使用的憑證。 如果憑證頒發機構是私人的，例如使用 Active Directory 和 Windows 憑證頒發機構進行內部部署，您可以用幾種方法將憑證Microsoft Teams 會議室新到憑證：
  
- 您可以將主控台加入 Active Directory，並自動新增所需的憑證，因為憑證頒發機構已發佈至 Active Directory (一般部署選項) 。
    
- 您可以在映射程式之後手動安裝憑證。 執行此操作之前，您必須完成 [主機的初始設定](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>若要手動安裝憑證

1. 將 CA 憑證下載到您的電腦，並將其儲存為"C：\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"。
    
2. 將主機放在系統管理模式 (請參閱 [系統管理模式和裝置管理](rooms-operations.md#AdminMode)) 。
    
3. 執行下列命令：
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 網域 (選) 
<a name="Certs"> </a>

您可以加入Microsoft Teams 會議室網域。 Microsoft Teams 會議室電腦工作站的個別 OU 中，因為許多工作站策略與電腦Microsoft Teams 會議室。 常見的範例是密碼強制執行政策，Microsoft Teams 會議室自動啟動。 有關 GPO 設定管理的資訊，請參閱管理[Microsoft Teams 會議室。](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>若要加入Microsoft Teams 會議室網域

1. 請從系統管理員帳戶 (主機，請參閱系統管理 [模式](rooms-operations.md#AdminMode)) 。
    
2. 啟動提升的 Powershell 命令提示。
    
3. 在 Powershell 中輸入下列命令：
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

例如，如果您的完整網域是 redmond.corp.microsoft.com，而您想要您的 Microsoft Teams 會議室 主機位於 「Microsoft Teams 會議室」 OU 中，且該 OU 為 「資源」OU 的子級，則命令為：
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果您想要在將電腦加入網域時重新命名，請使用 -NewName 標號，後面接著電腦的新名稱。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams 會議室部署檢查清單
<a name="Checklist"> </a>

使用下列檢查清單進行主機及其所有周邊設備已完全配置的最終驗證：
  
**應用程式設定**

|完成 |檢查 |
|:-----:|:-----|
|☐   |會議室帳戶名稱和電話 # (PSTN 啟用) 正確顯示   |
|☐   |Windows正確設定電腦名稱稱 (遠端系統管理)    |
|☐   |系統管理員帳戶密碼設定及驗證   |
|☐   |已應用所有固件更新   |
   
**音訊/視音訊周邊**

|完成 |檢查 |
|:-----:|:-----|
|☐   |若適用，相機外 (固件版本)    |
|☐   |相機功能與位置最佳   |
|☐   |設定預設裝置和播放預設通訊裝置設為預定的音訊周邊裝置   |
|☐   |設定預設通訊裝置設定為預定的音訊周邊裝置   |
|☐   |音訊周邊固件版本正確無誤 (適用)    |
|☐   |音訊輸入裝置可運作且位置最佳   |
|☐   |音訊輸出裝置可運作且位置最佳   |

**主控台**

|完成 |檢查 |
|:-----:|:-----|
|☐   |纜線安全且不會捏合   |
|☐   |HDMI 上的音訊輸入功能   |
|☐   |在 HDMI 上輸入視像功能   |
|☐   |主機可以自由旋轉   |



   
## <a name="see-also"></a>另請參閱
<a name="Checklist"> </a>

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
