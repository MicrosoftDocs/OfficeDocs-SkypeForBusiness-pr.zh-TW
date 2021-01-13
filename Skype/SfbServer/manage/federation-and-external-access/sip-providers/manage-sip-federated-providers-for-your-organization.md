---
title: 管理貴組織的 SIP 同盟提供者
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 瞭解如何為 SIP 同盟提供者的使用者設定支援。
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823563"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>在商務用 Skype Server 中管理組織的 SIP 同盟提供者

若要為 SIP 同盟提供者的使用者設定支援，您需要執行下列作業：

  - 設定一或多個外部使用者存取原則，以支援與 SIP 同盟提供者連絡人的通訊

  - 指定您要支援的主控提供者

  - 指定您要支援的公用 IM 提供者

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或編輯公用 SIP 同盟提供者

公用立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM 與公用提供者所提供的 IM 服務使用者通訊。

商務用 Skype 伺服器具有立即訊息的公用提供者設定。 每個公用提供者都會使用提供者的 Edge Server 完整網域名稱，以及預設驗證層級 **[僅允許使用者與其連絡人清單上使用此提供者的人通訊]** 來設定。

預設設定為不啟用任何公用提供者。 在啟用公用提供者之前，您應該先完成授權合約及佈建工作。 您可以在完成授權和佈建工作之前啟用提供者。 在必要工作完成之前，使用者將無法與這些提供者的連絡人通訊。 如需授權及布建公用提供者的詳細資訊，請參閱 [設定原則以控制公用使用者](../external-access-policies/configure-policies-to-control-public-user-access.md)訪問。

請使用下列程式來建立或編輯公用提供者。


### <a name="to-create-or-edit-public-providers"></a>建立或編輯公用提供者

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，依序按一下 **[同盟和外部存取]** 和 **[SIP 同盟提供者]**。

4.  如果您需要建立新的公用提供者，請依序按一下 **[新增]** 和 **[公用提供者]**。

5.  如果您需要編輯公用提供者清單中的項目，選取公用提供者，然後依序按一下 **[編輯]** 和 **[顯示詳細資料]**。

6.  在 **[編輯 SIP 同盟提供者]** 頁面上，您可以鍵入或編輯下列設定：
    
      - **[允許與這個提供者的通訊]**    選取此設定可讓 IM 與此提供者的使用者通訊。
    
      - **提供者名稱：**    必要內容，請輸入提供者的名稱，其將反映在 SIP 同盟提供者清單中。
    
      - **Access Edge service (FQDN) ：**   必要的屬性，請輸入您要設定之提供者的 Access Edge service 的完整功能變數名稱。 此資訊是以預設專案提供，只在公用提供者對公用提供者的 Access Edge service 的 FQDN 進行變更時，才應變更。
    
      - **[預設驗證層級：]**    預設設定，**[僅允許使用者與其連絡人清單上使用此提供者的人通訊]** 會限制與您已接受並且在您的連絡人清單中的連絡人通訊。
        
        選取 **[允許使用者與使用此提供者的所有人通訊]** 會移除您必須已收到並接受連絡人邀請的限制。此設定不會限制誰可以從公用提供者網路與您連絡。

7.  完成設定之後，請按一下 **[認可]** 儲存，或按一下 **[取消]** 捨棄您的變更。

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或編輯主控的 SIP 同盟提供者

主控提供者立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM，與託管提供者所提供之 IM 服務的使用者進行通訊。

每個裝載提供者都設有提供者的 Edge Server 完整網域名稱，以及預設驗證層級 [允許使用者僅與其連絡人清單中使用此提供者的人通訊]。

請使用下列程式來建立或編輯主控的提供者。

### <a name="to-create-or-edit-hosted-providers"></a>建立或編輯裝載提供者

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，按一下 [同盟及外部存取]，然後按一下 [SIP 同盟提供者]。

4.  如果您需要建立新的裝載提供者，請按一下 [新增]，然後按一下 [裝載提供者]。

5.  如果您需要編輯裝載提供者清單中的項目，請選取裝載提供者，按一下 [編輯]，然後按一下 [顯示詳細資料]。

6.  在「編輯 SIP 同盟提供者」頁面上，您可以輸入或編輯下列設定：
    
      - **允許與這個提供者的通訊**   選取此設定可與這個提供者的使用者進行通訊。
    
      - **提供者名稱：**    必要內容，請輸入提供者的名稱，其將反映在 SIP 同盟提供者清單中。
    
      - **Access Edge service (FQDN) ：**   必要的屬性，請輸入您要設定之主控提供者的 Access Edge service 的完整功能變數名稱。 此資訊應由主控的提供者提供，而且只有在主控提供者對主控提供者的 Access Edge service 的 FQDN 進行變更時，才應變更此資訊。
    
      - **預設驗證層級：**    預設設定，[允許使用者僅與其連絡人清單中使用此提供者的人通訊] 會將通訊範圍限制為您已接受並且在連絡人清單中的連絡人。
        
        選取 [允許使用者與使用此提供者的所有人通訊] 會移除您必須收到並接受連絡人邀請的限制。此設定不限制哪些人可以從裝載提供者的網路連絡您。

7.  完成設定時，按一下 [認可] 以儲存，或按一下 [取消] 以捨棄變更。


## <a name="see-also"></a>另請參閱


[設定原則以控制公用使用者的加入](../external-access-policies/configure-policies-to-control-public-user-access.md)

[啟用或停用同盟和公用 IM 連線](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

