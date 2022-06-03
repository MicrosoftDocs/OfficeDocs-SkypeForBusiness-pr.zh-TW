---
title: 在拓撲的伺服器上安裝商務用 Skype Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 摘要：瞭解如何在拓撲的每部伺服器上安裝商務用 Skype Server系統元件。
ms.openlocfilehash: 7aea6d25edcd28ba611b81d33eceed4172019bee
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860614"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>在拓撲的伺服器上安裝商務用 Skype Server
 
**總結：** 瞭解如何在拓撲的每部伺服器上安裝商務用 Skype Server系統元件。
  
將拓撲載入中央管理Microsoft Store，且 Active Directory 知道哪些伺服器會執行哪些角色，您必須在拓撲中的每部伺服器上安裝商務用 Skype Server系統。 您可以依任何循序執行步驟 1 到 5。 不過，您必須依序執行步驟 6、7 和 8，以及依照圖表中所述的步驟 1 到 5 之後執行。 安裝商務用 Skype Server系統是步驟 8 的步驟 7。
  
![概觀圖表。](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>安裝商務用 Skype Server系統

發佈拓撲之後，您可以在拓撲的每部伺服器上安裝商務用 Skype Server元件。 本節將引導您安裝商務用 Skype Server並設定前端集區的伺服器角色，以及與前端伺服器共置的任何伺服器角色。 若要安裝和設定伺服器角色，請在您要安裝伺服器角色的每部電腦上執行 [商務用 Skype Server 部署精靈]。 您可以使用部署精靈來完成所有四個部署步驟，包括安裝本機設定存放區、安裝前端伺服器、設定憑證，以及啟動服務。
  
> [!IMPORTANT]
> 您必須先使用拓撲產生器來完成和發佈拓撲，才能在伺服器上安裝商務用 Skype Server。 
  
> [!NOTE]
> 必須針對拓撲中的所有伺服器完成此程式。 
  
> [!CAUTION]
> 第一次啟動服務時，在前端伺服器上安裝商務用 Skype Server之後，您必須確定Windows防火牆服務正在伺服器上執行。 
  
> [!CAUTION]
> 遵循這些步驟之前，請確定您已使用同時是本機系統管理員和 RTCUniversalServerAdmins 群組成員的網域使用者帳戶登入伺服器。 
  
> [!NOTE]
> 如果您之前尚未在此伺服器上執行商務用 Skype Server安裝程式，系統會提示您輸入安裝的磁片磁碟機和路徑。 如果您的組織需要，或您有空間考慮，這可讓您安裝到系統磁片磁碟機以外的磁片磁碟機。 您可以將 [**安裝** 程式] 對話方塊中商務用 Skype Server檔案的安裝位置路徑變更為新的可用磁片磁碟機。 如果您將安裝程式檔案安裝到此路徑，包括OCSCore.msi，則其餘商務用 Skype Server檔案也會部署到該處。
  
> [!IMPORTANT]
> 開始安裝之前，請先使用 Windows Update，確定 Windows Server 是最新的。 
  
![Windows Server 為最新狀態。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>安裝商務用 Skype Server系統

1. 插入商務用 Skype Server安裝媒體。 如果安裝程式未自動開始，請按兩下 [ **安裝程式]**。
    
2. 安裝媒體需要Microsoft Visual C++才能執行。 隨即會出現一個對話方塊，詢問您是否要安裝它。 按一下 **[是]。**
    
3. 仔細檢閱授權合約，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按一下 [ **確定]**。 
    
4. 智慧型安裝程式是商務用 Skype Server中的一項功能，您可以在安裝程式期間連線到網際網路以檢查來自 Microsoft Update (MU) 的更新，如圖所示。 這可確保您有最新的產品更新，以提供更好的體驗。 按一下 **[安裝]** 開始安裝。
    
    > [!NOTE]
    > 許多組織都已在其公司環境中部署Windows Server Update Services (WSUS) 。 WSUS 可讓系統管理員完全管理透過 Microsoft Update 發行到其網路中電腦的更新散發。 作為累積更新 1 版本的一部分，商務用 Skype Server導入智慧型安裝程式與 WSUS 搭配運作的支援。 第一次部署商務用 Skype Server或使用 In-Place 升級功能從 Lync Server 2013 環境升級的 WSUS 客戶，會讓智慧型安裝程式從 WSUS 擷取Windows更新的Skype，而不是從 MU 擷取更新。 想要使用智慧型安裝程式的客戶必須先在所有電腦上執行 SmartSetupWithWSUS.psq，才能執行Setup.exe。 
  
     ![智慧型安裝程式螢幕擷取畫面。](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. 在 [部署精靈] 頁面上，按一下 [**安裝或更新商務用 Skype Server系統]**。
    
6. 執行下列程式中的程式，當您完成這些程式時，按一下 [ **結束** ] 以關閉 [部署精靈]。 針對集區中的每個前端伺服器重複這些程式。
    
### <a name="step-1-install-local-configuration-store"></a>步驟 1：安裝本機設定Microsoft Store

1. 檢閱必要條件，**然後按一下****步驟 1：安裝本** 機設定Microsoft Store旁的 [執行]。
    
    > [!NOTE]
    > 本機設定Microsoft Store是中央管理Microsoft Store的唯讀複本。 在Standard Edition部署中，中央管理Microsoft Store會使用前端伺服器上 SQL Server Express 版本的本機複本來建立。 當您執行 Prepare First Standard Edition Server 程式時，就會發生這種情況。 在Enterprise Edition部署中，當您發佈包含Enterprise Edition前端集區的拓撲時，會建立中央管理存放區。 
  
2. 在 [**安裝本機設定Microsoft Store**] 頁面上，確定已選取 [**直接從中央管理存放區擷取**] 選項，然後按 [**下一步]**。
    
    SQL Server Express版安裝在本機伺服器上。 本機設定存放區需要 SQL Server Express Edition。
    
3. 當本機伺服器設定安裝完成時，按一下 **[完成]**。
    
### <a name="step-2-set-up-or-remove-skype-for-business-server-components"></a>步驟 2：設定或移除商務用 Skype Server元件

1. 檢閱必要條件，**然後按一下** **[步驟 2：安裝或移除商務用 Skype Server元件**] 旁的 [執行]。
    
2. 在 [**設定商務用 Skype Server元件**] 頁面上，按 [**下一步**] 以設定已發佈拓撲中定義的元件。
    
3. [ **執行** 命令] 頁面會在設定發生時顯示命令和安裝資訊的摘要。 完成後，您可以使用清單來選取要檢視的記錄，然後按一下 [ **檢視記錄]**。
    
4. 當商務用 Skype Server元件設定完成，而且您已視需要檢閱記錄時，請按一下 **[完成**] 以在安裝中完成此步驟。
    
    > [!NOTE]
    > 如果系統提示 (，則重新開機伺服器，如果需要安裝) Windows桌面體驗，可能會發生這種情況。 當電腦備份並執行時，您必須再次執行此 (步驟 2：安裝或移除商務用 Skype Server元件) 程式。 
  
    > [!NOTE]
    > 如果安裝程式找到任何尚未滿足的必要條件，您將會收到「不符合必要條件」訊息的通知，如圖所示。 滿足必要的必要條件，然後 (步驟 2：設定或移除商務用 Skype Server元件) 程式再次啟動此程式。 
  
     ![必要條件。](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. 確認前兩個步驟如預期般完成。 確認有綠色核取記號，其文字為 **Complete**，如圖所示。
    
     ![安裝元件完成的前兩個步驟。](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. 再次 **執行 Windows Update**，以檢查安裝 商務用 Skype Server 元件之後是否有任何更新。
    
### <a name="step-3-request-install-or-assign-certificates"></a>步驟 3：要求、安裝或指派憑證

1. 檢閱必要條件， **然後按一下** **[步驟 3：要求]、[安裝] 或 [指派憑證]** 旁的 [執行]。
    
    > [!NOTE]
    > 商務用 Skype Server包含 SHA-2 套件的支援， (SHA-2 使用摘要長度 224、256、384 或 512 位) 摘要雜湊，以及從執行Windows 10、Windows 8、Windows 7、Windows Server 2012 R2 的用戶端連線簽署演算法，Windows Server 2012或Windows Server 2008 R2 作業系統。 若要使用 SHA-2 套件支援外部存取，外部憑證是由公用 CA 所簽發，該 CA 也可以發行具有相同位長度摘要的憑證。 
  
    > [!IMPORTANT]
    > 選取哪一個雜湊摘要和簽署演算法取決於將使用憑證的用戶端和伺服器，以及用戶端和伺服器將與誰通訊的其他電腦和裝置，也必須知道如何使用憑證中使用的演算法。 如需作業系統和某些用戶端應用程式中支援哪些摘要長度的資訊，[請參閱 Windows PKI 部落格 - SHA2 和 Windows](/archive/blogs/pki/sha2-and-windows)。 
  
    每個Standard Edition或前端伺服器最多需要四個憑證：oAuthTokenIssuer 憑證、預設憑證、Web 內部憑證和 Web 外部憑證。 不過，您可以要求並指派具有適當主體別名專案的單一預設憑證，以及 oAuthTokenIssuer 憑證。 如需憑證需求的詳細資訊，請[參閱 商務用 Skype Server 環境](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)需求或[2019 商務用 Skype Server伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。
    
    > [!IMPORTANT]
    > 下列程式描述如何從內部 Active Directory 憑證服務的憑證授權單位單位設定憑證。 
  
2. 在 **[憑證精靈]** 頁面中，按一下 **[要求]**。
    
3. 在 [ **憑證要求** ] 頁面上填入相關資料，包括選取 [SIP 網域] 和 ，然後按 [ **下一步]**。
    
4. 在 [**延遲或立即要求**] 頁面上，您可以按一下 [**下一步**]，接受 [**立即將要求傳送至線上憑證授權單位單位**] 選項。 如果您選取此選項，則必須提供具有自動線上註冊的內部 CA。 如果您選擇延遲要求的選項，系統會提示您輸入名稱和位置來儲存憑證要求檔案。 憑證要求必須由組織內部的 CA 或公用 CA 來呈現和處理。 接著，您必須匯入憑證回應，並將它指派給適當的憑證角色。
    
5. 在 [**選擇憑證授權單位單位 (CA)**] 頁面上，選取 [**從您環境中偵測到的清單中選取 CA**] 選項，然後從清單中選取透過 Active Directory 網域服務) CA 註冊的已知 (。 或者，選取 [ **指定另一個憑證授權單位單位** ] 選項，在方塊中輸入另一個 CA 的名稱，然後按 [ **下一步]**。
    
6. 在 [ **憑證授權單位單位帳戶]** 頁面上，系統會提示您輸入認證，以在 CA 要求及處理憑證要求。 您應該已經判斷是否需要使用者名稱和密碼，才能事先要求憑證。 您的 CA 系統管理員將擁有必要的資訊，而且可能必須協助您進行此步驟。 如果您需要提供替代認證，請選取核取方塊，在文字方塊中提供使用者名稱和密碼，然後按 [ **下一步]**。
    
7. 在 [ **指定替代憑證範本** ] 頁面上，若要使用預設的 Web 服務器範本，請按 [ **下一步]**。
    
    > [!NOTE]
    > 如果您的組織已建立範本作為預設 Web 服務器 CA 範本的替代方案，請選取核取方塊，然後輸入替代範本的名稱。 您將需要 CA 系統管理員所定義的範本名稱。 
  
8. 在 [**名稱和安全性設定**] 頁面上，指定 [**易記名稱]**。 藉由使用易記名稱，您可以快速識別憑證和用途。 如果您將它保留空白，則會自動產生名稱。 設定金鑰的 **位長度** ，或接受預設值 2048 位。 如果您判斷憑證和私密金鑰需要移動或複製到其他系統，請選取 [將憑 **證的私密金鑰標示為可匯出** ]，然後按 [ **下一步]**。
    
    > [!NOTE]
    > 商務用 Skype Server的可匯出私密金鑰需求最少。 其中一個這類位置是在集區的 Edge Server 上，其中媒體轉送驗證服務會使用憑證複本，而不是集區中每個實例的個別憑證。 
  
9. 在 [ **組織資訊]** 頁面上，選擇性地提供組織資訊，然後按 [ **下一步]**。
    
10. 在 [ **地理資訊]** 頁面上，選擇性地提供地理資訊，然後按 [ **下一步]**。
    
11. 在 [ **主體名稱/主體替代名稱** ] 頁面上，檢閱將新增的主體別名，然後按 [ **下一步]**。
    
12. 在 [ **SIP 網域設定** ] 頁面上，選取 **[SIP 網域**]，然後按 [ **下一步]**。
    
13. 在 [ **設定其他主體替代名稱** ] 頁面上，新增任何其他必要的主體別名，包括未來其他 SIP 網域可能需要的任何名稱，然後按 [ **下一步]**。
    
14. 在 [ **憑證要求摘要]** 頁面上，檢閱摘要中的資訊。 如果資訊正確，請按 [ **下一步]**。 如果您需要更正或修改設定，請按一下 **[回到** 適當的頁面] 進行更正或修改。
    
15. 在 **[執行命令]** 頁面上，按 **[下一步]**。
    
16. 在 [ **線上憑證要求狀態]** 頁面上，檢閱傳回的資訊。 您應該會注意到憑證已發行並安裝到本機憑證存放區。 如果回報它已發行並安裝，但無效，請確定 CA 根憑證已安裝在伺服器的受根信任 CA 存放區中。 請參閱 CA 檔，瞭解如何擷取受信任的根 CA 憑證。 如果您需要檢視擷取的憑證，請按一下 [ **檢視憑證詳細資料]**。 預設會選取 [**將憑證指派給商務用 Skype Server憑證使用量] 複** 選框。 如果您想要手動指派憑證，請清除核取方塊，然後按一下 [ **完成]**。
    
17. 如果您在上一頁清除 [**將憑證指派給商務用 Skype Server憑證使用量**] 核取方塊，您將會看到 [**憑證指派**] 頁面。 按 **[下一步]**。
    
18. 在 [**憑證Microsoft Store**] 頁面上，選取您要求的憑證。 如果您想要檢視憑證，請按一下 [ **檢視憑證詳細資料**]，然後按 [ **下一步** ] 繼續。
    
    > [!NOTE]
    > 如果 **[線上憑證要求狀態** ] 頁面回報憑證發生問題，例如憑證無效，請檢視實際憑證以取得解決問題的協助。 導致憑證不正確兩個特定問題是先前提及的遺失受根信任 CA 憑證，以及與憑證相關聯的遺漏私密金鑰。 請參閱您的 CA 檔以解決這兩個問題。
  
19. 在 [ **憑證指派摘要]** 頁面上，檢閱呈現的資訊以確定這是應該指派的憑證，然後按 [ **下一步]**。
    
20. 在 [ **執行** 命令] 頁面上，檢閱命令的輸出。 如果您想要檢閱指派程式，或是否發出錯誤或警告，請按一下 [ **檢視** 記錄檔]。 當您完成檢閱時，按一下 [ **完成]**。
    
21. 在 [憑 **證精靈** ] 頁面上，確認所有服務都有綠色複選，以指出所有服務都已獲指派憑證，包括 OAuthTokenIssuer，如圖所示，然後按一下 [ **關閉]**。
    
     ![已正確安裝和指派憑證。](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > 如果您要在實驗室環境中安裝，而且剛剛使用 Active Directory 憑證服務設定憑證授權單位單位，您必須重新開機執行憑證服務的伺服器和前端伺服器，憑證指派才能順利通過。 
  
    > [!TIP]
    >  如需 Active Directory 憑證服務中憑證的詳細資訊，請參閱 [Active Directory 憑證服務](/windows/deployment/deploy-whats-new)。 
  
### <a name="step-4-start-services"></a>步驟 4：啟動服務

1. 檢閱 **步驟 4：啟動服務** 的必要條件。
    
2. 如果這是至少有三部伺服器的Enterprise Edition前端集區，則會使用Windows Fabric，而且您必須使用 **Start-CsPool** Cmdlet。 如果使用單一伺服器，這一律是Standard Edition的情況，您會使用 **Start-CsWindowsService** Cmdlet。 在此範例中，我們會使用集區中具有三部前端伺服器的Enterprise Edition、開 **啟 商務用 Skype Server 管理命令接** 口，然後執行 **Start-CsPool** Cmdlet，如圖所示。 對於所有其他角色，包括Standard Edition伺服器，您必須使用 **Start-CsWindowsService**。 若要部署前端角色以外的角色，請參閱這些特定角色的檔。
    
     ![啟動商務用 Skype服務。](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. 在 **[執行命令]** 頁面上順利啟動所有服務之後，按一下 **[完成]**。
    
    > [!IMPORTANT]
    > 啟動伺服器上服務的命令是回報服務實際上已啟動的最佳方法。 它可能不會反映服務的實際狀態。 建議您使用步驟 **服務狀態 (選擇性)** 開啟 Microsoft Management Console (MMC) ，並確認服務已成功啟動，如圖所示。 如果有任何商務用 Skype Server服務尚未啟動，您可以在 MMC 中以滑鼠右鍵按一下該服務，然後按一下 [**啟動]**。 
  
     ![確認服務已啟動。](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
