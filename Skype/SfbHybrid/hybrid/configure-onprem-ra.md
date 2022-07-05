---
title: 在 2019 年 商務用 Skype Server 中設定資源帳戶
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
ms.localizationpriority: medium
ms.collection: ''
description: 設定 商務用 Skype Server 2019 的資源帳戶。
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615609"
---
# <a name="configure-resource-accounts"></a>設定資源帳戶

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

商務用 Skype Server 2019 混合式實作只會使用電話系統提供的雲端服務進行統一傳訊，且不會與Exchange Online整合。 在 2019 商務用 Skype Server，您現在可以使用[Microsoft 365 或 Office 365 中電話系統](/MicrosoftTeams/here-s-what-you-get-with-phone-system)所述的雲端通話佇列和自動語音應答。

若要在 2019 商務用 Skype Server使用電話系統自動語音應答或通話佇列，您必須建立作為應用程式端點並可指派電話號碼的資源帳戶，然後使用線上 Teams 系統管理中心來設定通話佇列或自動語音應答。 您可以在線上使用此資源帳戶 (請參閱 [在 Microsoft Teams 中管理資源帳戶](/MicrosoftTeams/manage-resource-accounts) ，以建立位於線上) 或內部部署的資源帳戶，如本文所述。 一般而言，您會有多個電話系統自動語音應答或通話佇列節點，每個節點都會對應至資源帳戶，這些帳戶可在線上或在 2019 商務用 Skype Server中使用。

如果您有現有的 Exchange UM 自動語音應答和通話佇列系統，在切換至 Exchange Server 2019 或 Exchange Online 之前，您必須手動記錄如下所述的詳細資料，然後使用 Teams 系統管理中心實作全新的系統。

## <a name="overview"></a>概觀

如果您的電話系統自動語音應答或通話佇列將需要服務號碼，則可依下列順序符合各種相依性：

1. 取得服務號碼。
2. 取得免費[Microsoft Teams 電話資源帳戶授權](/MicrosoftTeams/teams-add-on-licensing/virtual-user)或付費電話系統授權，以搭配資源帳戶使用。
3. 建立資源帳戶。 需要自動語音應答或通話佇列，才能有相關聯的資源帳戶。
4. 等候線上與內部部署之間的 Active Directory 同步。
5. 將電話系統授權指派給資源帳戶。
6. 將服務號碼指派給資源帳戶。
7. 建立電話系統通話佇列或自動語音應答。
8. 將資源帳戶與自動語音應答或呼叫佇列建立關聯： (New-CsApplicationInstanceAssociation) 。

如果自動語音應答或通話佇列以巢狀方式置於最上層自動語音應答下，則相關聯的資源帳戶只需要電話號碼，如果您想要多個進入自動語音應答和通話佇列結構的點數。

若要將通話重新導向至您組織中常用線上的人員，他們必須擁有 **電話系統** 授權並啟用企業語音或具有 Microsoft 365 或Office 365通話方案。 請參閱 [指派 Microsoft Teams 授權](/MicrosoftTeams/assign-teams-licenses)。 若要啟用企業語音，您可以使用 Windows PowerShell。 例如，執行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

如果您建立的電話系統自動語音應答或通話佇列是巢狀的，而且不需要電話號碼，則程式如下：

1. 建立資源帳戶  
2. 等候線上與內部部署之間的 Active Directory 同步處理
3. 建立電話系統自動語音應答或通話佇列
4. 將資源帳戶與電話系統自動語音應答或通話佇列建立關聯

## <a name="create-a-resource-account-with-a-phone-number"></a>建立具有電話號碼的資源帳戶

建立使用電話號碼的資源帳戶需要以下列循序執行下列工作：

1. 移植或取得付費或免付費服務號碼。 無法將號碼指派給任何其他語音服務或資源帳戶。

   將電話號碼指派給資源帳戶之前，您必須先取得或移植現有的付費或免付費服務號碼。 取得付費或免付費服務電話號碼之後，這些電話號碼會顯示在 **Microsoft Teams 系統管理中心**  >  **語音**  >  **電話號碼** 中，而列出 **的號碼類型** 會列為 **服務 - 免付費電話**。 若要取得您的服務號碼，請參閱 [取得服務電話號碼](/MicrosoftTeams/getting-service-phone-numbers) ，或如果您想要轉移現有的服務號碼，請參閱將 [電話號碼轉移至 Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。

   如果您不在美國，就無法使用 Microsoft Teams 系統管理中心來取得服務號碼。 請改為移至[管理組織的電話號碼](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)，以查看如何從美國外部執行此動作。

2. 購買電話系統授權。 請參閱：  
   - [Microsoft Teams 電話資源帳戶授權](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 企業版 E1 和 E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 企業版 E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 企業版 E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 針對每個電話系統自動語音應答或通話佇列執行 `New-CsHybridApplicationEndpoint` Cmdlet 來建立內部部署資源帳戶，並為每個使用者提供名稱、sip 位址等等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    如需此命令的詳細資訊，請參閱 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

4.  (選擇性) 建立資源帳戶之後，您可以等候 AD 在線上與內部部署之間同步，或強制同步處理並繼續線上設定電話系統自動語音應答或通話佇列。 若要強制同步處理，您會在執行 AAD Connect (的電腦上執行下列命令 (如果您尚未這麼做，您必須載入 `import-module adsync` 才能執行命令) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    如需此命令的詳細資訊，請參閱 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

    請注意，此時帳戶可能已同步處理，但布建可能尚未完成。  檢查 [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)的輸出。  如果同步處理的端點尚未完成布建，則不會顯示在這裡。  您可以在 M365 入口網站的 [[Teams 安裝](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)狀態] 下檢查布建要求的狀態。  此布建階段最多可能需要 24 小時。

5. 將 **Microsoft Teams 電話資源帳戶** 授權或 **Teams 電話標準方案** 授權指派給資源帳戶。 請參閱 [指派 Microsoft Teams 附加元件授權](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) 和 [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

   如果您要將電話號碼指派給資源帳戶，您現在可以使用免費 **Microsoft Teams 電話資源帳戶** 授權。 這可為組織層級的電話號碼提供電話系統功能，並可讓您建立自動語音應答和通話佇列功能。

6. 將服務號碼指派給資源帳戶。 `Set-CsHybridApplicationEndpoint`使用 命令來指派電話號碼 (並使用 -LineURI 選項) 至資源帳戶。

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    如需此命令的詳細資訊，請參閱 [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。

    若要將直接路由或混合式號碼指派給資源帳戶，請使用下列 Cmdlet：

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   如果資源帳戶將指派給最上層自動語音應答或通話佇列，則需要指派的電話號碼。 使用者 (訂閱者) 無法將電話號碼指派給資源帳戶，只能使用服務付費電話號碼或免付費電話號碼。

     您可以將直接路由或混合式號碼指派給您的資源帳戶。 如需詳細資訊，請參閱 [規劃直接路由](/MicrosoftTeams/direct-routing-plan) 和 [規劃雲端自動語音應答](plan-cloud-auto-attendant.md)。

     > [!NOTE]
     > 僅 Microsoft Teams 使用者和代理程式支援指派給資源帳戶的直接路由服務號碼，自動語音應答和通話佇列。

7. 建立電話系統自動語音應答或通話佇列。 請參閱下列其中一項：

   - [設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. 將資源帳戶與您先前選擇的電話系統自動語音應答或通話佇列建立關聯。

## <a name="create-a-resource-account-without-a-phone-number"></a>建立不含電話號碼的資源帳戶

本節討論如何建立位於內部部署的資源帳戶。 在 [Microsoft Teams 中管理資源](/MicrosoftTeams/manage-resource-accounts)帳戶討論如何建立線上的資源帳戶。

無論您要建立全新的電話系統自動語音應答或通話佇列結構，或是重建原先在 Exchange UM 中建立的結構，都需要執行這些步驟。

登入商務用 Skype前端伺服器，然後執行下列 PowerShell Cmdlet：

1. 針對每個電話系統自動語音應答或通話佇列執行 `New-CsHybridApplicationEndpoint` Cmdlet 來建立內部部署資源帳戶，並為每個使用者提供名稱、sip 位址等等。

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    如需此命令的詳細資訊，請參閱 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。

2.  (選擇性) 建立資源帳戶之後，您可以等候 AD 在線上與內部部署之間同步，或強制同步處理並繼續線上設定電話系統自動語音應答或通話佇列。 若要強制同步處理，您會在執行 AAD Connect (的電腦上執行下列命令 (如果您尚未這麼做，您必須載入 `import-module adsync` 才能執行命令) ：

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    如需此命令的詳細資訊，請參閱 [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。

3. 建立電話系統自動語音應答或通話佇列。 請參閱下列其中一項：
   - [設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. 將資源帳戶與電話系統建立關聯自動語音應答或您先前選擇的通話佇列。

## <a name="test-the-implementation"></a>測試實作

測試實作的最佳方式是呼叫電話系統自動語音應答或通話佇列設定的號碼，並聯機到其中一個代理程式或功能表。 您也可以使用系統管理中心 [動作] 窗格中的 [ **測試] 按鈕** ，快速地進行測試呼叫。 如果您想要變更電話系統自動語音應答或通話佇列，請選取它，然後在 [動作] 窗格中按一下 [**編輯]**。 

> [!TIP]
> 如果您的資源帳戶無法指派給通話佇列或自動語音應答，請參閱[Microsoft Teams 的已知問題](/MicrosoftTeams/Known-issues#phone-system)和[如何修正我的混合式應用程式實例](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)一節中的 Microsoft Teams 部落格。

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>將 Exchange UM 自動語音應答或通話佇列移至電話系統

從 Exchange UM 移轉至電話系統將需要重新建立通話佇列和自動語音應答結構，不支援直接從一個移轉到另一個。 若要重新實作一組通話佇列和自動語音應答：

1. 以系統管理員身分登入，在 Exchange 2013 或 2016 系統上執行下列命令，以取得所有 Exchange UM 自動語音應答和通話佇列的清單：

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. 針對每個列出的 Exchange UM 呼叫佇列或自動語音應答，請記下其在結構、設定中的位置，並取得相關聯聲音或文字轉換語音檔案的複本， (輸出中的 guid 會是檔案儲存) 的資料夾名稱。 您可以執行 命令來取得這些詳細資料：

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    如需此命令的詳細資訊，請參閱 [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。 您可能需要擷取的完整選項清單位於 [UMAutoAttendant 成員](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) ，但要記下的最重要選項是：

    - 營業時間
    - 非上班時間
    - 語言
    - 假日排程

3. 如先前所述，建立新的內部部署端點。
   指派最上層自動語音應答暫存編號以供測試之用。

4. 設定使用端點的電話系統自動語音應答或通話佇列，如先前所述。

5. 測試電話系統自動語音應答或通話佇列。

6. 將連結至 Exchange UM 通話佇列或自動語音應答的電話號碼重新指派給對應的電話系統自動語音應答或通話佇列。  

   此時，如果您已經移轉 UM 語音信箱，您應該能夠移轉至 2019 Exchange Server。

## <a name="see-also"></a>另請參閱

[建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)

[什麼是雲端自動語音應答？](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[規劃雲端自動語音應答](plan-cloud-auto-attendant.md)

[規劃雲端通話佇列](plan-call-queue.md)

[為內部部署使用者規劃雲端語音信箱服務](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[在 Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( 中管理資源帳戶建立線上首頁的資源帳戶\)