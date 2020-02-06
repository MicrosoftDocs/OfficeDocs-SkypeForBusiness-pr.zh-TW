---
title: 設定原則以控制遠端使用者存取
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: 您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype 伺服器使用者共同作業。 若要控制遠端使用者存取權，您可以在全域、網站和使用者層級設定原則。
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818294"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中設定控制遠端使用者存取權的原則

您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype 伺服器使用者共同作業。 若要控制遠端使用者存取權，您可以在全域、網站和使用者層級設定原則。 網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。 如需有關您可以設定之原則類型的詳細資料，請參閱[管理商務用 Skype Server 的同盟及外部存取](../managing-federation-and-external-access.md)。 在一個策略層級套用的商務用 Skype 伺服器原則設定，可以覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。

> [!NOTE]  
> 您可以設定控制遠端使用者存取的原則，即使您的組織未啟用遠端使用者存取權也一樣。 不過，您設定的原則只會在您的組織啟用遠端使用者存取時生效。 此外，如果您指定使用者原則來控制遠端使用者存取，則原則只適用于已啟用商務用 Skype Server 且設定為使用原則的使用者。 如需指定可從遠端位置登入商務用 Skype 伺服器的使用者的詳細資料，請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。

使用下列程式來設定您要用來控制遠端使用者存取權的每個外部存取原則。


> [!NOTE]  
> 這個程式說明如何設定原則，只讓它能夠與遠端使用者通訊，但您設定支援遠端使用者存取的每個原則也都可以設定聯盟使用者存取與公用使用者存取。 如需有關設定支援同盟使用者之原則的詳細資訊，請參閱[在商務用 Skype Server 中設定控制聯盟使用者存取權的原則](configure-policies-to-control-federated-user-access.md)。 如需有關設定原則以支援公用使用者的詳細資料，請參閱[在商務用 Skype Server 中管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>設定外部存取原則以支援遠端使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 頁面上，執行下列其中一項操作：
    
      - 若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
      - 若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。 在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。 在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立一個代表使用者原則所涵蓋內容的唯一名稱（例如，為遠端使用者啟用通訊的使用者原則的**EnableRemoteUsers** ）。
    
      - 若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。

6.  請執行下列其中一項操作：
    
      - 若要啟用此原則的遠端使用者存取權，請選取 [**啟用與遠端使用者的通訊**] 核取方塊。
    
      - 若要停用遠端使用者對原則的存取權，請清除 [**啟用與遠端使用者的通訊**] 核取方塊。

7.  按一下 [認可]****。

若要啟用遠端使用者存取，您也必須在您的組織中啟用遠端使用者存取的支援。 如需詳細資訊，請參閱[啟用或停用同盟與公用 IM](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線。

如果這是使用者原則，您也必須將原則套用到您想要能夠遠端連線的使用者。 如需詳細資訊，請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。
