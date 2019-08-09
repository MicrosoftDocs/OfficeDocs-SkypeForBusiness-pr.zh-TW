---
title: 在商務用 Skype Server 2019 中設定資源帳戶
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 針對商務用 Skype Server 2019 設定資源帳戶。
ms.openlocfilehash: a307a5ed40c52579020f4cd0eef6646afdb15649
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253952"
---
# <a name="configure-resource-accounts"></a>設定資源帳戶

商務用 Skype Server 2019 混合式實現只使用電話系統提供的雲端服務來進行整合訊息, 而且不要與 Exchange Online 整合。 在商務用 Skype Server 2019 中, 您現在可以使用「雲端通話佇列」和「自動語音應答」,[以下是您在 Office 365 中使用電話系統所取得的內容](/MicrosoftTeams/here-s-what-you-get-with-phone-system)。

若要在商務用 Skype Server 2019 中使用電話系統自動語音應答或通話佇列, 您需要建立充當應用程式端點且可獲指派電話號碼的資源帳戶, 然後使用線上團隊系統管理中心來設定通話佇列或自動語音應答。 此資源帳戶可以連線 (請參閱在[Microsoft 團隊中管理資源](/MicrosoftTeams/manage-resource-accounts)帳戶以在線上建立資源帳戶) 或內部部署 (請見本文所述)。 通常您會有多個電話系統自動語音應答或通話佇列節點, 每個節點都對應至可在線上或商務用 Skype Server 2019 中駐留的資源帳戶。

如果您有現有的 Exchange UM 自動語音應答及呼叫佇列系統, 在您切換到 Exchange Server 2019 或 Exchange online 之前, 您將需要手動記錄詳細資料, 然後使用 [團隊系統管理中心] 來執行全新的系統。.

## <a name="overview"></a>概觀

如果您的電話系統自動語音應答或通話佇列將需要服務號碼, 就可以依照下列順序來符合各種相依性:

1. 取得服務號碼
2. 取得免費的電話系統-[虛擬使用者授權](/MicrosoftTeams/teams-add-on-licensing/virtual-user)或付費電話系統授權, 以便與資源帳戶搭配使用。
3. 建立資源帳戶。 需要自動語音應答或通話佇列, 才能擁有關聯的資源帳戶。
4. 在線上與內部部署之間等待 active directory 同步處理。
5. 將電話系統授權指派給資源帳戶。
6. 將服務號碼指派給資源帳戶。
7. 建立電話系統通話佇列或自動語音應答。
8. 將資源帳戶與自動語音應答或通話佇列建立關聯: (新-CsApplicationInstanceAssociation)。

如果自動語音應答或呼叫佇列是嵌套在頂層自動語音應答底下, 只要您想要將多個進入點輸入到自動語音應答及呼叫佇列的結構中, 相關聯的資源帳戶就只需要電話號碼。

若要將來電重新導向至組織中的目前線上人員, 他們必須具備**電話系統**授權, 且可供企業語音使用或擁有 Office 365 通話方案。 請參閱[指派 Microsoft 團隊授權](/MicrosoftTeams/assign-teams-licenses)。 若要啟用企業語音, 您可以使用 Windows PowerShell。 例如, 執行:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

如果您要建立的電話系統自動語音應答或通話佇列將會嵌套, 且不需要電話號碼, 程式如下:

1. 建立資源帳戶  
2. 在線上與內部部署之間等待 active directory 同步處理
3. 建立電話系統自動語音應答或通話佇列
4. 將資源帳戶與電話系統自動語音應答或通話佇列建立關聯

## <a name="create-a-resource-account-with-a-phone-number"></a>使用電話號碼建立資源帳戶

若要建立使用電話號碼的資源帳戶, 必須以下列循序執行下列工作:

1. 移植或取得付費或免付費服務號碼。 該號碼不能指派給任何其他語音服務或資源帳戶。

   將電話號碼指派給資源帳戶之前, 您將需要取得或移植現有的付費或免付費服務號碼。 當您收到付費或免付費服務電話號碼之後, 就會顯示在**Microsoft 團隊系統管理中心** > **語音** > **電話號碼**中, 而列出的**數位類型**則會列為 [**服務-免付費**電話]。 若要取得您的服務號碼, 請參閱[取得服務電話號碼](/MicrosoftTeams/getting-service-phone-numbers), 或者如果您想要轉移現有的服務號碼, 請參閱[將電話號碼轉移至 Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365)。

   如果您在美國以外, 您就無法使用 Microsoft 團隊系統管理中心來取得服務號碼。 移至 [[管理貴組織的電話號碼](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)], 瞭解如何從美國以外的地區進行。

2. 購買電話系統授權。 請參閱  
   - [電話系統-虛擬使用者授權](/MicrosoftTeams/teams-add-on-licensing/virtual-user.md)
   - [Office 365 企業版 E1 和 E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 企業版 E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 企業版 E5 商務版軟體](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 針對每個電話系統自動語音應答或通話`New-CsHybridApplicationEndpoint`佇列執行 Cmdlet 來建立內部部署資源帳戶, 並為每個系統提供名稱、sip 位址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    如需更多關於此命令的詳細資料, 請參閱[新-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

4. 可選建立資源帳戶之後, 您可以在線上與內部部署之間等待 AD 同步, 或強制執行同步處理並繼續進行手機系統自動語音應答或通話佇列的線上設定。 若要強制進行同步處理, 您可以在執行 AAD 連接的電腦上執行下列命令 (如果您尚未這麼做, 則必須載入`import-module adsync`才能執行命令):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    如需此命令的詳細資料, 請參閱[開始 ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

5. 將電話系統-虛擬使用者或電話系統授權指派給資源帳戶。 請參閱[指派 Microsoft 團隊授權](/MicrosoftTeams/assign-teams-licenses)及[指派授權給一個使用者](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。

   如果您要將電話號碼指派給資源帳戶, 您現在可以使用 [免付費電話系統-虛擬使用者授權]。 這會提供手機系統功能給組織階層的電話號碼, 並可讓您建立自動語音應答及呼叫佇列功能。


6. 將服務號碼指派給資源帳戶。 使用`Set-CsHybridApplicationEndpoint`命令, 將電話號碼 (使用-LineURI 選項) 指派給資源帳戶。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    如需此命令的詳細資料, 請參閱[設定 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。

    若要將直接路由或混合式編號指派給資源帳戶, 請使用下列 Cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

如果資源帳戶將指派給最上層的自動語音應答或通話佇列, 就需要指派的電話號碼。 使用者 (訂閱者) 電話號碼無法指派給資源帳戶, 只能使用服務付費或免付費電話號碼。

  您可以將直接路由混合式數位指派給您的資源帳戶。  如需詳細資訊, 請參閱[規劃直接路由](/MicrosoftTeams/direct-routing-plan.md)。

  > [!NOTE]
  > 只有 Microsoft 團隊使用者和代理程式才支援指派給自動語音應答之資源帳戶的直接路由服務號碼和通話佇列。

7. 建立電話系統自動語音應答或通話佇列。 請參閱下列其中一項:

   - [設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 將資源帳戶與您先前選擇的電話系統自動語音應答或通話佇列建立關聯。

小型企業版中的小型企業實施方案範例[-設定自動](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)語音應答及[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。

## <a name="create-a-resource-account-without-a-phone-number"></a>建立不含電話號碼的資源帳戶

本節討論如何建立駐留在內部部署的資源帳戶。 若要在[Microsoft 團隊的 [管理資源帳戶] 中](/MicrosoftTeams/manage-resource-accounts)討論如何建立以線上為宿主的資源帳戶。

無論您是建立全新的電話系統自動語音應答或通話佇列結構, 或是在 Exchange UM 中最初建立的結構, 都必須執行這些步驟。

登入商務用 Skype 前端伺服器, 並執行下列 PowerShell Cmdlet:

1. 針對每個電話系統自動語音應答或通話`New-CsHybridApplicationEndpoint`佇列執行 Cmdlet 來建立內部部署資源帳戶, 並為每個系統提供名稱、sip 位址等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    如需更多關於此命令的詳細資料, 請參閱[新-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

2. 可選建立資源帳戶之後, 您可以在線上與內部部署之間等待 AD 同步, 或強制執行同步處理並繼續進行手機系統自動語音應答或通話佇列的線上設定。 若要強制進行同步處理, 您可以在執行 AAD 連接的電腦上執行下列命令 (如果您尚未這麼做, 則必須載入`import-module adsync`才能執行命令):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    如需此命令的詳細資料, 請參閱[開始 ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

3. 建立電話系統自動語音應答或通話佇列。 請參閱下列其中一項:
   - [設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 將資源帳戶與電話系統自動語音應答或您先前選擇的通話佇列建立關聯。

小型企業版中的小型企業實施方案範例[-設定自動](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)語音應答及[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。

## <a name="test-the-implementation"></a>測試實施

測試實現的最佳方式是撥打電話系統自動語音應答或呼叫佇列的號碼, 並聯機至其中一個代理程式或功能表。 您也可以使用系統管理中心動作窗格中的 [**測試] 按鈕**, 快速進行測試通話。 如果您想要變更手機系統自動語音應答或通話佇列, 請選取該選項, 然後在 [動作] 窗格中按一下 [**編輯**]。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>將 Exchange UM 自動語音應答或呼叫佇列移至電話系統

從 Exchange UM 到手機系統的遷移需要重新建立通話佇列和自動語音應答結構, 而不支援直接從其中一個遷移到另一個。 若要重新實現一組通話佇列和自動語音應答:

1. 在 Exchange 2013 或2016系統上執行下列命令, 以系統管理員身分登入, 以取得所有 Exchange UM 自動語音應答和通話佇列的清單:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 針對每個列出的 Exchange UM 通話佇列或自動語音應答, 請記下其在結構中的位置、設定, 以及取得相關音效或文字轉換語音檔案的複本 (輸出中的 guid 將是儲存檔案的資料夾名稱)。 您可以執行以下命令來取得這些詳細資料:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    請參閱[UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) , 以取得更多關於此命令的詳細資料。 您可能需要捕獲的完整選項清單是在[UMAutoAttendant 成員](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx), 但最重要的選項如下所示:

    - 商務時間
    - 非商務時間
    - 語言
    - 假日排程

3. 如先前所述, 建立新的內部部署端點。
   將最上層的自動語音應答指派成暫時的號碼以進行測試。

4. 根據先前所述, 設定使用端點的電話系統自動語音應答或通話佇列。

   您可能會發現在使用「小型企業版」的教學課程中使用練習, 您可以[設定自動](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)語音應答, 在舊版 Exchange UM 系統中建立階層的邏輯地圖。
5. 測試電話系統自動語音應答或通話佇列。
6. 將連結至 Exchange UM 通話佇列或自動語音應答的電話號碼重新指派給對應的電話系統自動回應或通話佇列。  

   此時, 如果您已經遷移了 UM 語音信箱, 您應該位於遷移到 Exchange Server 2019 的位置。

## <a name="see-also"></a>請參閱

[建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)

[什麼是雲端自動語音應答？](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[規劃雲端自動語音應答](plan-cloud-auto-attendant.md)

[規劃雲端通話佇列](plan-call-queue.md)

[為內部部署使用者規劃雲端語音信箱服務](plan-cloud-voicemail.md)

[新-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[管理 Microsoft 團隊](/MicrosoftTeams/manage-resource-accounts) - \(中的資源帳戶以建立以線上方式駐留的資源帳戶\)
