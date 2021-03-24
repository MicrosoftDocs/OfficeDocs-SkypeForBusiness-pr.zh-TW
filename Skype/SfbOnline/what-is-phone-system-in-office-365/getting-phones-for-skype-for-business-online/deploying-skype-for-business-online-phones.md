---
title: 部署用商務用 Skype Online 電話
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 瞭解部署步驟以取得正確的固件、如有必要更新、指派授權，以及設定商務用 Skype Online 電話的設定
ms.openlocfilehash: 4c683cd2b0259c0145632c8522f3b262c686c71d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097099"
---
# <a name="deploying-skype-for-business-online-phones"></a>部署用商務用 Skype Online 電話

此為部署指南，可協助部署商務用 Skype Online IP 電話。
  
在所有類型的企業中，擁有電話號碼可讓使用者撥打和接聽語音電話，這是進行商務的重要需求。 擁有電話號碼的使用者將能夠在所有商務用 Skype 裝置上撥打語音通話，包括 IP 電話、電腦和行動裝置。 您可以閱讀取得商務用 Skype Online 電話，深入瞭解商務用 Skype IP [電話](getting-phones-for-skype-for-business-online.md)。
  
## <a name="deployment-steps-for-ip-phones"></a>IP 電話的部署步驟

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>步驟 1 - 下載製造商的系統管理員指南和電話手冊

在您開始使用之前，建議先下載手機制造商的管理指南和電話使用者手冊。
  
- 針對 Polycom 電話，請參閱 [Poly 文件庫](https://documents.polycom.com/category/voice)。
    
- 針對 Yealink 手機，請參閱 [Yealink 商務用 Skype HD SIP 電話解決方案](http://www.yealink.com/products_top_2.html)。
    
- 針對 AudioCodes 手機，請參閱 [音訊代碼資源建構管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>步驟 2 - 確認您購買或移移商務用 Skype 支援的 IP 電話和固件

商務用 Skype Online 支援的手機和固件也與商務用 Skype Server 相容，但情況並不一定相反。 若要確定您購買或置備支援的手機和固件，請參閱取得商務用 [Skype Online 的手機](getting-phones-for-skype-for-business-online.md)。
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>步驟 3 - 檢查已安裝正確的固件，並在需要時更新固件

檢查手機上的固件版本。 適用于：
  
- **Polycom VVX 手機**，請前往 **設定**  >  **狀態**  >  **平臺**  >  **應用程式**  >  **主。**
    
- **Yealink 手機**，前往 **主電話** 畫面上的狀態。
    
- **音訊代碼手機**，**從開始畫面** 前往功能表  >  **裝置**  >  狀態固件版本。
    
    > [!NOTE]
    > 若要遠端存取電話詳細資料，請參閱製造商管理指南。 請參閱上述使用者指南和電話手冊的連結。 
  
- **Lync Phone Edition (LPE) 手機**，從開始畫面前往功能表  >  系統資訊。
    
### <a name="step-4---device-update-considerations"></a>步驟 4 - 裝置更新注意事項

> [!NOTE]
> 5.5.1.X 之前的 Polycom 固件具有製造商專用裝置鎖定機制，以商務用 Skype 的 「Phone-Lock」取代。 使用「Device-Lock」將使用「Device-Lock」保護的電話從 5.4.X.X 升級至 5.5.1.X，不會繼承「Device-Lock」的 PIN 碼，而「裝置鎖定」可能會讓電話不安全。 啟用「Device-Lock」的使用者必須啟用下列 Polycom 裝置設定檔參數，讓使用者控制升級時間 (lync.deviceUpdate.popUpSK.enabled=1) 。 
  
商務用 Skype 服務會管理固件更新。 每個經商務用 Skype 認證的電話的固件都會上傳到商務用 Skype Update 伺服器，且裝置更新預設會啟用所有電話。 根據電話和投票間隔上的非啟用時間，電話會自動下載並安裝最新的認證版本。 您可以使用 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) Cmdlet 將 _EnableDeviceUpdate_ 參數設定為 來停用裝置更新設定 `false` 。
  
![顯示部署電話的螢幕擷取畫面](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
當新的固件可供使用並準備好下載及安裝時，電話會通知使用者。 Polycom 電話會通知使用者，並提供使用者更新 **或延** 後 **的選項**。
  
![顯示更新和延後選項的螢幕擷取畫面。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
對於 Polycom 電話，您可以選取 **SwUpdate** 來更新手機上的固件。
  
![顯示 SwUpdate 選項的螢幕擷取畫面](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
您也可以選擇使用合作夥伴部署系統管理固件更新。 有關合作夥伴的撥備系統管理 ，包括進位電話自訂，請參閱製造商管理指南。
  
> [!CAUTION]
> 請確定有單一裝置更新授權 (帶內裝置更新或協力廠商) 伺服器，以避免更新迴圈。 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>步驟 5 - 設定與基礎結構電話設定

您可以使用商務用 Skype 帶內管理 Windows PowerShell Cmdlet 設定最常用的電話選項與政策。 請參閱 [Set-CsIPPhonePolicy，](/powershell/module/skype/Set-CsIPPhonePolicy) 瞭解這些參數和設定的詳細資訊。
  
有關網路基礎結構規劃，請參閱 [Skype 營運架構](https://www.skypeoperationsframework.com/)。
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>步驟 6 - 準備讓使用者進行登錄

若要讓使用者順利登錄商務用 Skype Online 電話並撥打電話，您必須確認使用者已指派正確的授權。 您至少需要指派電話系統授權和通話方案。 有關其他資訊，請參閱商務用 Skype 和 [Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 附加元件授權，以及指派商務用 Skype 和 Microsoft Teams [授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。
  
您可以閱讀電話系統與通話方案以進一步瞭解 [通話方案](/microsoftteams/calling-plan-landing-page)
  
- **線上使用者** 可用的登錄選項為：
    
  - 使用 **Polycom VVX 5XX/6XX** 電話的使用者會看到：
    
     ![顯示 Polycom 電話登入的螢幕擷取畫面](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - 使用 **Yealink T48G/T46G** 電話的使用者會看到：
    
     ![顯示 Yealink 手機登入的螢幕擷取畫面。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    有關製造商支援的登錄選項的詳細資訊，請參閱取得商務用 [Skype Online 的手機](getting-phones-for-skype-for-business-online.md)。
    
- **使用者識別碼** 使用者可以使用手機的鍵盤或螢幕小鍵盤 (如果) ，可以使用組織的使用者名稱和密碼來登錄電話。 例如，他們應該使用 UPN <em>格式，例如</em>  amosm@contoso.com 名稱。
    
     ![顯示登入畫面的螢幕擷取畫面](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > LPE 和合作夥伴 IP 電話版商務用 Skype Online 不支援 PIN 驗證。 
  
- **使用電腦** 當在乙太網路上 (BToE) 軟體已安裝並啟用時，使用者可以使用 Windows 商務用 Skype App 上的驗證視窗登入他們的電話。 請參閱 [步驟 7 (選 ](deploying-skype-for-business-online-phones.md#BK_BTOE)) - 如果您有裝置配對，且在乙太網路上 (更好搭配使用 BToE) 其他資訊。
    
  > [!NOTE]
  > 使用者必須使用組織的使用者名稱和密碼才能登錄電話。 例如，他們應該使用 UPN  <em>格式，例如</em>  amosm@contoso.com 名稱。
  
     ![顯示登入畫面的螢幕擷取畫面](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **使用 Web 登錄**：這是線上使用者使用標準網頁瀏覽器進行驗證的一種新方式。 當使用者使用瀏覽器進行登錄時，系統將會提供一組指示，以遵循這些指示。
    
  - 使用 **Polycom VVX 5XX/6XX** 電話的使用者會看到：
    
     ![顯示 Polycom 指示的螢幕擷取畫面](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - 使用 **Yealink T48G/T46G** 電話的使用者會看到：
    
     ![顯示 Yealink 指示的螢幕擷取畫面](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    產生的程式碼將在 15 分鐘後到期。 到期時，使用者必須按一下 [重試或確定」，以根據電話產生新代碼。
    
  - 使用 **Polycom VVX 5XX/6XX** 電話的使用者會看到：
    
     ![顯示已過期 Polycom 程式碼的螢幕擷取畫面](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - 使用 **Yealink T48G/T46G** 電話的使用者會看到：
    
     ![顯示過期的 Yealink 程式碼的螢幕擷取畫面](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    使用瀏覽器流覽至手機上顯示的位址，然後輸入您的商務用 Skype 使用者名稱。
    
     ![顯示電子郵件驗證的螢幕擷取畫面](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    輸入手機上顯示的代碼。
    
     ![顯示登入畫面上輸入代碼的螢幕擷取畫面](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    確認網站顯示「[手機制造商名稱] 商務用 **Skype 認證電話**」，然後按一下 [ **繼續**]。
    
     ![顯示名稱驗證的螢幕擷取畫面](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    按一下使用者的認證，或按一下 [ **使用另一個帳戶**：
    
     ![顯示認證選項的螢幕擷取畫面](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    顯示下列頁面時，可以安全地關閉瀏覽器。
    
     ![顯示確認訊息的螢幕擷取畫面](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > 商務用 Skype Online 的 LPE 電話僅支援透過 USB 連線來登錄。 
  
- **支援的部署** 下表顯示目前支援部署模型的支援驗證類型，包括 Exchange 整合、使用多重要素驗證的新式驗證 (MFA) ，以及商務用 Skype Online 和內部部署。
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**商務用 Skype** <br/> |**交換** <br/> |**電話Sign-In方法** <br/> |**商務用 Skype 存取** <br/> |**已停用新式驗證和 MFA 的 Exchange Access** <br/> |**已啟用新式驗證和 MFA 的 Exchange Access** <br/> |
|線上  <br/> |線上  <br/> |Web 登錄  <br/> |是  <br/> |是  <br/> |是  <br/> |
|線上  <br/> |線上  <br/> |使用者名稱/密碼  <br/> |是  <br/> |是  <br/> |否  <br/> |
|線上  <br/> |內部部署  <br/> |Web 登錄  <br/> |是  <br/> |否  <br/> |否  <br/> |
|線上  <br/> |內部部署  <br/> |使用者名稱/密碼  <br/> |是  <br/> |是  <br/> |否  <br/> |
|內部部署  <br/> |線上/內部部署  <br/> |PIN 驗證  <br/> |是  <br/> |否  <br/> |否  <br/> |
|內部部署  <br/> |線上/內部部署  <br/> |使用者名稱/密碼  <br/> |是  <br/> |是  <br/> |不適用  <br/> |
|內部部署  <br/> |線上/內部部署  <br/> |透過 PC 或 BTOE (登錄)   <br/> |是  <br/> |是  <br/> |不適用  <br/> |
   
- **電話功能** 根據 IP 電話合作夥伴的不同，功能集可能會稍有不同。 有關完整功能集，以及每個手機制造商功能詳細資訊，請參閱取得商務用 [Skype Online 手機](getting-phones-for-skype-for-business-online.md)。
    
- **Phone-Lock** 是商務用 Skype 認證電話中最近推出的一項功能，可用來保護電話。 如果已啟用，系統將會要求使用者在驗證成功時建立 PIN。 建立之後，電話會在您定義的閒置超時到期時鎖定、使用者手動鎖定手機，或是使用電話配對將手機鎖定與電腦鎖定同步處理。 如果電話鎖定 PIN 輸入錯誤數次，電話會登出使用者，或需要系統管理員程式碼才能解除鎖定電話，但這會因電話合作夥伴而異。 使用者的 PIN 應該介於 6 到 15 位數之間。
    
    您可以針對Phone-Lock停用 (預設為啟用的) 、變更閒置-超時，以及選擇使用者是否可以在鎖定時撥打電話，或是否使用 inband-settings。 請參閱 [Set-CsUCPhoneConfiguration，](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 以進一步瞭解這些設定的詳細資訊。
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>步驟 7 (選) - 如果您有裝置配對，且在乙太網路上更 (BToE) 
<a name="BK_BTOE"> </a>

BToE 是合作夥伴 IP 電話的一種電話問題機制，可讓使用者的電話與 Windows 商務用 Skype 應用程式配對。 BToE 可讓使用者：
  
- 使用商務用 Skype 桌面應用程式 (他們的 IP 電話) 
    
- 使用Phone-Lock同步處理
    
- 按一下以撥打
    
BToE 可配置為以兩種模式操作：  *自動*  (預設) 和 *手動*  。 對於使用商務用 Skype 帶 (設定) /停用的使用者，也可以啟用此功能。 在手動 *模式中*  操作時，使用者必須執行額外的步驟，以將手機與 Windows App 配對。
  
 **將 BToE 部署到使用者**
  
1. 使用電腦埠將電腦連接到手機。
    
     ![顯示電腦連接的螢幕擷取畫面](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 從下列連結從製造商網站下載並安裝最新的 BToE 軟體。 為了改善使用者體驗，您可以使用系統管理發佈解決方案 ，例如 Microsoft 端點組態管理員來發佈和安裝 BToE 軟體。 有關使用 Configuration Manager 的協助，請參閱 Configuration [Manager 中的套件和程式](/configmgr/apps/deploy-use/packages-and-programs)。
    
   - [Polycom BToE 軟體下載網站](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Yealink BToE 軟體下載](http://www.yealink.com/products_list_10.html)
    
   - [音訊代碼 BToE 軟體下載](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. 根據預設，BToE 的伺服器設定會設定為 **啟用****和** 自動模式。 若要變更這些設定，請參閱 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy)。
    
> [!NOTE]
> Mac 和 VDI 平臺目前不支援 BToE。 
  
## <a name="related-topics"></a>相關主題
[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[以下是可透過電話系統獲得的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音訊會議與通話方案的適用國家/地區](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
