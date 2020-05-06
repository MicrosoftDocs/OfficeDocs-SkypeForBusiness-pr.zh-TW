---
title: 在商務用 Skype Server 2019 中設定資源帳戶
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 為商務用 Skype Server 2019 設定資源帳戶。
ms.openlocfilehash: 0d7e52892c718f215a269201b73a547a97c13f96
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042840"
---
# <a name="configure-resource-accounts"></a>設定資源帳戶

商務用 Skype Server 2019 混合式的實現只會使用電話系統提供的雲端服務以進行整合通訊，而且不會與 Exchange Online 整合。 在商務用 Skype Server 2019 中，您現在可以使用下列所述的雲端通話佇列和自動語音應答，如下所述。[您可以使用 Office 365 中的電話系統取得什麼功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)。

若要使用電話系統自動語音應答或具有商務用 Skype Server 2019 的通話佇列，您將需要建立充當應用程式端點且可以指派電話號碼的資源帳戶，然後使用線上團隊系統管理中心來設定通話佇列或自動語音應答。 這個資源帳戶可在線上上進行（請參閱[管理 Microsoft 小組中的資源帳戶](/MicrosoftTeams/manage-resource-accounts)以建立線上資源帳戶）或內部部署（如本文所述）。 一般來說，您會有多個電話系統自動語音應答或通話佇列節點，每個節點都對應至可在線上或商務用 Skype Server 2019 中的資源帳戶。

如果您有現有的 Exchange UM 自動語音應答及通話佇列系統，在切換至 Exchange Server 2019 或 Exchange online 之前，您必須先手動記錄詳細資料，然後再使用團隊系統管理中心執行全新的系統。

## <a name="overview"></a>概觀

如果您的電話系統自動語音應答或通話佇列需要服務號碼，可依下列順序滿足各種相依性：

1. 取得服務號碼。
2. 取得免費的電話系統[虛擬使用者授權](/MicrosoftTeams/teams-add-on-licensing/virtual-user)或付費電話系統授權，以與資源帳戶搭配使用。
3. 建立資源帳戶。 必須有自動語音應答或通話佇列具有相關聯的資源帳戶。
4. 在線上和內部部署之間等候 active directory 同步處理。
5. 將電話系統授權指派給資源帳戶。
6. 將服務號碼指派給資源帳戶。
7. 建立電話系統通話佇列或自動語音應答。
8. 關聯資源帳戶與自動語音應答或通話佇列：（New-CsApplicationInstanceAssociation）。

如果 [自動語音應答] 或 [通話佇列] 嵌套在最上層的自動語音應答之下，只要您想要將多個專案點組成至自動語音應答及通話佇列的結構，相關聯的資源帳戶才需要電話號碼。

若要將來電重新導向至組織中的內部網路人員，他們必須具備**電話系統**授權，並可啟用 Enterprise Voice 或具備 Office 365 通話方案。 請參閱[指派 Microsoft 團隊附加元件授權](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)。 若要啟用企業語音，您可以使用 Windows PowerShell。 例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

如果您要建立的電話系統自動語音應答或通話佇列將會嵌套，而且不需要電話號碼，則程式為：

1. 建立資源帳戶  
2. 在線上和內部部署之間等候 active directory 同步處理
3. 建立電話系統自動語音應答或通話佇列
4. 關聯資源帳戶與電話系統自動語音應答或通話佇列

## <a name="create-a-resource-account-with-a-phone-number"></a>使用電話號碼建立資源帳戶

若要建立使用電話號碼的資源帳戶，必須依下列循序執行下列工作：

1. 埠或取得收費或免付費服務號碼。 無法將號碼指派給任何其他語音服務或資源帳戶。

   在您將電話號碼指派給資源帳戶之前，您必須先取得或接收您現有收費或免付費服務號碼的埠。 當您取得收費或免付費服務電話號碼後，他們會顯示在**Microsoft 小組系統管理中心** > **語音** > **電話號碼**中，而且所列的**號碼類型**會列為「**服務-免付費**」。 若要取得服務號碼，請參閱[取得服務電話號碼](/MicrosoftTeams/getting-service-phone-numbers)，如果您想要轉接現有的服務號碼，請參閱[將電話號碼轉移給小組](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。

   如果您是在美國境外，您就無法使用 Microsoft 團隊系統管理中心取得服務號碼。 請移至 [[管理組織的電話號碼](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)]，以瞭解如何從美國以外的國家/地區執行。

2. 購買電話系統授權。 請參閱：  
   - [電話系統-虛擬使用者授權](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 企業版 E1 和 E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 企業版 E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 企業版 E5 商務軟體](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 針對每個電話系統自動語音應答或通話`New-CsHybridApplicationEndpoint`佇列執行 Cmdlet，以建立內部部署資源帳戶，並提供每個名稱、sip 位址等的指令程式。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    如需此命令的詳細資訊，請參閱[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

4. 選建立資源帳戶後，您可以等候 AD 在線上和內部部署之間同步處理，或是強制進行同步處理，並繼續進行電話系統自動語音應答或通話佇列的線上設定。 若要強制進行同步處理，您可以在執行 AAD 連線的電腦上執行下列命令（如果您尚未執行此動作，則必須`import-module adsync`先載入才能執行命令）：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    如需此命令的詳細資訊，請參閱[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

5. 將電話系統虛擬使用者或電話系統授權指派給資源帳戶。 請參閱[指派 Microsoft 團隊附加元件授權](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)，並[指派授權給一位使用者](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。

   若要將電話號碼指派給資源帳戶，您現在可以使用「成本免費電話系統-虛擬」使用者授權。 這為組織層級的電話號碼提供電話系統功能，並讓您建立自動語音應答及通話佇列功能。


6. 將服務號碼指派給資源帳戶。 使用`Set-CsHybridApplicationEndpoint`命令將電話號碼（使用-LineURI 選項）指派給資源帳戶。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    請參閱[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)以取得更多有關此命令的詳細資料。

    若要將直接路由或混合式號碼指派給資源帳戶，請使用下列 Cmdlet：

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   若要將其指派給最上層的自動語音應答或通話佇列，則資源帳戶需要指派的電話號碼。 無法將使用者（訂戶）電話號碼指派給資源帳戶，只能使用服務收費或免付費電話號碼。

     您可以將直接路由或混合式號碼指派給資源帳戶。 如需詳細資訊，請參閱[Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) And [plan Cloud auto](plan-cloud-auto-attendant.md)direct。

     > [!NOTE]
     > 指派給自動語音應答和通話佇列之資源帳戶的直接路由服務編號，僅支援 Microsoft 團隊使用者和代理程式。

7. 建立電話系統自動語音應答或通話佇列。 請參閱下列其中一項：

   - [設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 將資源帳戶與您先前所選擇的電話系統自動語音應答或通話佇列相關聯。

小型企業可使用小型企業的範例範例[-設定自動](/microsoftteams/tutorial-org-aa)語音應答和[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。

## <a name="create-a-resource-account-without-a-phone-number"></a>建立沒有電話號碼的資源帳戶

本節討論如何建立駐留在內部部署的資源帳戶。 若要在[Microsoft 小組的 [管理資源帳戶] 中](/MicrosoftTeams/manage-resource-accounts)討論如何建立以線上處理的資源帳戶。

您必須執行這些步驟，不論您是建立全新的電話系統自動語音應答或通話佇列結構，或是最初在 Exchange UM 中建立的結構重建。

登入商務用 Skype 前端伺服器，並執行下列 PowerShell Cmdlet：

1. 針對每個電話系統自動語音應答或通話`New-CsHybridApplicationEndpoint`佇列執行 Cmdlet，以建立內部部署資源帳戶，並提供每個名稱、sip 位址等的指令程式。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    如需此命令的詳細資訊，請參閱[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

2. 選建立資源帳戶後，您可以等候 AD 在線上和內部部署之間同步處理，或是強制進行同步處理，並繼續進行電話系統自動語音應答或通話佇列的線上設定。 若要強制進行同步處理，您可以在執行 AAD 連線的電腦上執行下列命令（如果您尚未執行此動作，則必須`import-module adsync`先載入才能執行命令）：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    如需此命令的詳細資訊，請參閱[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

3. 建立電話系統自動語音應答或通話佇列。 請參閱下列其中一項：
   - [設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 關聯先前所選的資源帳戶和電話系統自動語音應答或通話佇列。

小型企業可使用小型企業的範例範例[-設定自動](/microsoftteams/tutorial-org-aa)語音應答和[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。

## <a name="test-the-implementation"></a>測試實施

測試實現的最佳方式是呼叫為電話系統自動語音應答或通話佇列設定的號碼，並連接至其中一個代理程式或功能表。 您也可以使用 [系統管理中心] 動作窗格中的 [**測試] 按鈕**，快速進行測試呼叫。 如果您想變更電話系統自動語音應答或通話佇列，請選取它，然後按一下動作窗格中的 [**編輯**]。 

> [!TIP]
> 如果資源帳戶對通話佇列或自動語音應答指派困難，請參閱 microsoft 小組的[已知問題](/MicrosoftTeams/Known-issues#phone-system)，以及 Microsoft 小組博客中的[如何修正混合應用程式實例](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)一節。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>將 Exchange UM 自動語音應答或通話佇列移至電話系統

從 Exchange UM 向電話系統進行遷移時，將需要重新建立通話佇列和自動語音應答結構，但不支援直接從一個遷移至另一個。 若要重新執行一組呼叫佇列和自動語音應答：

1. 在以系統管理員身分登入的 Exchange 2013 或2016系統上執行下列命令，以取得所有 Exchange UM 自動語音應答及通話佇列的清單。

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 針對每個列出的 Exchange UM 通話佇列或自動語音應答，請注意其在結構中的位置、設定，以及取得關聯的聲音或文字語音轉換檔案的副本（輸出中的 guid 將是儲存檔案的資料夾名稱）。 您可以執行下列命令來取得這些詳細資料：

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    如需這個命令的詳細資訊，請參閱[Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。 您可能需要捕獲的完整選項清單是在[disable-umautoattendant 成員](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx)，但是最重要的附注如下：

    - 營業時間
    - 非上班時間
    - 語言
    - 假日排程

3. 如先前所述，建立新的內部部署端點。
   將最上層的自動語音應答指派給用於測試目的的臨時號碼。

4. 如先前所述，設定電話系統自動語音應答或使用端點的通話佇列。

   您可能會發現使用「[小型企業」範例](/microsoftteams/tutorial-org-aa)中的練習，設定自動語音應答來建立舊 Exchange UM 系統中階層的邏輯對應。
5. 測試電話系統自動語音應答或通話佇列。
6. 將連結至 Exchange UM 通話佇列或自動語音應答的電話號碼重新指派至對應的電話系統自動語音應答或通話佇列。  

   此時，如果您已遷移 UM 語音信箱，您應該位於遷移至 Exchange Server 2019 的位置。

## <a name="see-also"></a>另請參閱

[建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)

[什麼是雲端自動語音應答？](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[規劃雲端自動語音應答](plan-cloud-auto-attendant.md)

[規劃雲端通話佇列](plan-call-queue.md)

[規劃內部部署使用者的雲端語音信箱服務](plan-cloud-voicemail.md)

[新 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[管理 Microsoft 小組](/MicrosoftTeams/manage-resource-accounts) - \(中的資源帳戶，以建立位於線上的資源帳戶\)
