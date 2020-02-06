---
title: 管理組織的 SIP 同盟提供者
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 瞭解如何設定 SIP 聯盟提供者的使用者支援。
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818364"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>在商務用 Skype Server 中管理貴組織的 SIP 聯盟提供者

若要針對 SIP 聯盟提供者的使用者設定支援，您必須執行下列動作：

  - 設定一或多個外部使用者存取原則，以支援與 SIP 聯盟提供者連絡人的通訊

  - 指定您要支援的託管提供者

  - 指定您想要支援的公用 IM 提供者

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或編輯公用 SIP 聯盟提供者

公用立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與公用提供者所提供的 IM 服務使用者通訊。

商務用 Skype 伺服器具有立即訊息的公用提供者配置。 每個公開提供者都是使用提供者的邊緣伺服器完整功能變數名稱來設定，而且預設驗證層級**可讓使用者只與他們的連絡人清單中使用這個提供者的人通訊**。

預設設定為 [未啟用任何公用提供者]。 在啟用公用提供者之前，您應該先完成授權協定和置備作業。 您可以先啟用提供者，然後才能完成授權及預配作業。 在完成先決條件工作完成之前，使用者將無法與這些提供者上的連絡人通訊。 如需授權與提供公用提供者的詳細資料，請參閱[設定控制公用使用者](../external-access-policies/configure-policies-to-control-public-user-access.md)訪問的原則。

使用下列程式來建立或編輯公用提供者。


### <a name="to-create-or-edit-public-providers"></a>建立或編輯公用提供者

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [ **SIP 同盟提供者**]。

4.  如果您需要建立新的公用提供者，請按一下 [**新增**]，然後按一下 [**公用提供者**]。

5.  如果您需要從公用提供者清單中編輯專案，請選取公用提供者，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

6.  在 [**編輯 SIP 聯盟提供者**] 頁面上，您可以輸入或編輯下列設定：
    
      - **啟用與此提供者**   的通訊選取此設定即可啟用與此提供者使用者的 IM。
    
      - **提供者名稱：**   required 屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者清單中。
    
      - **[存取邊緣服務（FQDN）]：**   [必要] 屬性，請輸入您要設定之提供者的存取邊緣服務的完整功能變數名稱。 此資訊是以預設專案提供的，只有在公用提供者變更公用提供者的存取邊緣服務的 FQDN 時，才能加以變更。
    
      - **預設驗證階層：**   預設設定是 [**允許使用者與連絡人清單中的人員通訊]，使用這個提供者**時，會將通訊限制在您已接受的連絡人，並在您的連絡人清單中。
        
        選取 [**允許使用者與使用這個提供者的所有人通訊**]，就會移除您必須收到並接受連絡人邀請的限制。 此設定不會限制誰能從公用提供者的網路與您聯繫。

7.  設定完畢後，請按一下 [**認可**] 來儲存，或按一下 [**取消**] 放棄您的變更。

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或編輯託管 SIP 聯盟提供者

宿主提供者立即訊息（IM）連線可讓貴組織中的使用者使用 IM 與託管提供者所提供之 IM 服務的使用者通訊。

每個託管提供者都是以提供者的 Edge 伺服器的完整功能變數名稱進行設定，而且預設驗證層級**可讓使用者只與他們的連絡人清單中使用這個提供者的人通訊**。

使用下列程式來建立或編輯託管提供者。

### <a name="to-create-or-edit-hosted-providers"></a>建立或編輯託管提供者

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [ **SIP 同盟提供者**]。

4.  如果您需要建立新的託管提供者，請按一下 [**新增**]，然後按一下 [**託管提供者**]。

5.  如果您需要編輯託管提供者清單中的專案，請選取託管提供者，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

6.  在 [**編輯 SIP 聯盟提供者**] 頁面上，您可以輸入或編輯下列設定：
    
      - **啟用與此提供者**   的通訊選取此設定，即可與此提供者的使用者進行通訊。
    
      - **提供者名稱：**   required 屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者清單中。
    
      - **[存取邊緣服務（FQDN）]：**   [必要] 屬性，請輸入您要設定之託管提供者的存取邊緣服務的完整功能變數名稱。 此資訊應該由託管提供者提供，而且只有在託管提供者對託管提供者的存取邊緣服務的 FQDN 進行變更時，才應進行變更。
    
      - **預設驗證階層：**   預設設定是 [**允許使用者與連絡人清單中的人員通訊]，使用這個提供者**時，會將通訊限制在您已接受的連絡人，並在您的連絡人清單中。
        
        選取 [**允許使用者與使用這個提供者的所有人通訊**]，就會移除您必須收到並接受連絡人邀請的限制。 此設定不會限制誰能從主機託管提供者的網路與您聯繫。

7.  設定完畢後，請按一下 [**認可**] 來儲存，或按一下 [**取消**] 放棄您的變更。


## <a name="see-also"></a>請參閱


[設定控制公用使用者進行控制的原則](../external-access-policies/configure-policies-to-control-public-user-access.md)

[啟用或停用同盟和公用 IM 連線](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

