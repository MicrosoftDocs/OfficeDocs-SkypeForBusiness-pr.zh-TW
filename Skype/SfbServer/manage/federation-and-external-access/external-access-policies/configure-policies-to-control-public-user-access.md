---
title: 設定控制公用使用者存取的原則
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ublic 立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM 與公用 IM 服務提供者所提供的 IM 服務的使用者進行通訊。
ms.openlocfilehash: 2482270d27843b546246e11fb1bcadcc45c900da
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774953"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中設定原則以控制公用使用者存取

公用立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM 與公用 IM 服務提供者所提供的 IM 服務的使用者進行通訊。 您可以設定一或多個外部使用者存取原則，以控制公用使用者是否可以與內部商務用 Skype Server 使用者共同作業。 公用立即訊息連線功能是一項附加的功能，可依賴您的部署和使用者的設定。 它也取決於公用 IM 提供者的服務布建。 

若要控制公用使用者存取權，您可以在全域、網站和使用者層級設定原則。 商務用 Skype Server 于一個原則層級套用的原則設定，會覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。

在 IM 邀請方面，回應將視用戶端軟體而定。除非使用者設定的規則 (亦即，在使用者用戶端的 [允許] 和 [封鎖] 清單中) 明確封鎖外部傳送者，否則會接受要求。另外，如果使用者已選擇封鎖所有不在其 [允許] 清單內的 IM 使用者，IM 邀請也會遭到封鎖。



> [!NOTE]  
> 即便您並未對所屬組織啟用同盟關係，仍可設定原則來控制公用使用者存取。 不過，只有當您為組織啟用同盟關係時，所設定的原則才會生效。 如需啟用同盟的詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。 此外，如果您指定使用者原則以控制公用使用者存取，則原則只適用于已啟用商務用 Skype Server 的使用者，且設定為使用原則。 如需指定可登入商務用 Skype Server 之公用使用者的詳細資訊，請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。


請使用下列步驟來設定原則，以支援一個或多個公用 IM 提供者的使用者存取。

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>設定外部存取原則以支援公用使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，依序按一下 [外部使用者存取] 及 [外部存取原則]。

4.  在「外部存取原則」頁面中，執行下列其中一項：
    
      - 若要設定全域原則以支援公用使用者存取，依序按一下全域原則、[編輯] 和 [顯示詳細資料]。
    
      - 若要建立新的網站原則，請按一下 [新增]，然後按一下 [站台原則]。在 [選取站台] 的清單中按一下適當網站，然後按一下 [確定]。
    
      - 若要建立新的使用者原則，按一下 [新增]，再按一下 [使用者原則]。在 [新的外部存取原則] 中，於 [名稱] 欄位中建立唯一名稱以代表使用者原則的涵蓋範圍 (例如，建立 **EnablePublicUsers** 的使用者原則以啟用公用使用者的通訊功能)。
    
      - 若要變更現有原則，按一下表中所列之適當原則，然後按一下 [編輯]，接著按一下 [顯示詳細資料]。

5.  (選用) 如果您想要新增或編輯說明，請在 [說明] 中指定原則資訊。

6.  執行下列其中一項作業：
    
      - 若要啟用原則的公用使用者存取功能，請選取 [啟用與公用使用者的通訊] 核取方塊。
    
      - 若要停用原則的公用使用者存取功能，請清除 [啟用與公用使用者的通訊] 核取方塊。

7.  按一下 **[認可]**。

若要啟用公用使用者存取功能，則您必須同時對組織啟用同盟關係支援。 如需詳細資訊，請參閱[在商務用 Skype Server 中設定控制同盟使用者存取的原則](configure-policies-to-control-federated-user-access.md)。

如果這是使用者原則，您也必須將該原則套用至您希望能夠與公用使用者共同作業的公用使用者。 


## <a name="see-also"></a>另請參閱

[管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
