---
title: 設定原則以控制公用使用者存取
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: ublic 立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與公用 IM 服務提供者所提供的 IM 服務使用者通訊。
ms.openlocfilehash: d661ca9a4ef7840cbc955d0c999ae5a1490a63cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818304"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中設定控制公用使用者存取權的原則

公用立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與公用 IM 服務提供者所提供之 IM 服務的使用者通訊。 您可以設定一或多個外部使用者存取原則，以控制公用使用者是否可與內部商務用 Skype 伺服器使用者共同作業。 公用立即訊息連線能力是一項額外的功能，可依賴您的部署與使用者的設定。 它也取決於在公用 IM 提供者上提供服務的功能。 

若要控制公用使用者的存取權，您可以在全域、網站和使用者層級設定原則。 在一個策略層級套用的商務用 Skype 伺服器原則設定，可以覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。

在 IM 邀請的情況下，回應會視用戶端軟體而定。 除非由使用者設定的規則明確封鎖外部寄件者（也就是使用者的用戶端**允許**及**封鎖**清單中的設定），否則就會接受該要求。 此外，如果使用者想要封鎖來自不在其 [**允許**] 清單中的使用者的所有 IM，也可以封鎖 im 邀請。



> [!NOTE]  
> 您可以設定原則來控制公用使用者的存取，即使您的組織未啟用同盟也一樣。 不過，您設定的原則只會在您的組織啟用同盟時生效。 如需啟用同盟的詳細資料，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。 此外，如果您指定使用者原則來控制公用使用者存取，則原則只適用于已啟用商務用 Skype Server 且設定為使用原則的使用者。 如需有關指定可以登入商務用 Skype Server 的公用使用者的詳細資料，請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。


使用下列程式來設定原則，以支援由一或多個公用 IM 提供者的使用者存取。

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>設定外部存取原則以支援公用使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 頁面上，執行下列其中一項操作：
    
      - 若要設定全域原則以支援公用使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
      - 若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。 在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。 在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，可為公用使用者進行通訊的使用者原則的**EnablePublicUsers** ）。
    
      - 若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。

6.  請執行下列其中一項操作：
    
      - 若要針對原則啟用公用使用者存取，請選取 [**啟用與公用使用者的通訊**] 核取方塊。
    
      - 若要停用公用使用者對原則的存取權，請清除 [**啟用與公用使用者的通訊**] 核取方塊。

7.  按一下 [認可]****。

若要啟用公用使用者存取，您也必須在您的組織中啟用同盟支援。 如需詳細資訊，請參閱[在商務用 Skype Server 中設定控制聯盟使用者存取權的原則](configure-policies-to-control-federated-user-access.md)。

如果這是使用者原則，您也必須將原則套用到您想要能夠與公用使用者共同作業的公用使用者。 


## <a name="see-also"></a>請參閱

[管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
