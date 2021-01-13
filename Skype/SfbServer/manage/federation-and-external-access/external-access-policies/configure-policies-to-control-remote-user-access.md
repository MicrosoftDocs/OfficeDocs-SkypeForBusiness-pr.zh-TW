---
title: 設定控制遠端使用者存取的原則
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: 您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype Server 使用者共同作業。 若要控制遠端使用者存取，您可以在全域、網站及使用者層級設定原則。
ms.openlocfilehash: 0fd24f7c57cfaa4a131bcd1648cb1b6e6eb5f05a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817293"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中設定原則以控制遠端使用者存取

您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部商務用 Skype Server 使用者共同作業。 若要控制遠端使用者存取，您可以在全域、網站及使用者層級設定原則。 網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。 如需您可以設定之原則類型的詳細資訊，請參閱 [管理同盟和外部存取商務用 Skype Server](../managing-federation-and-external-access.md)。 在一個原則層級套用的商務用 Skype 伺服器原則設定，可以覆寫在另一個原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。

> [!NOTE]  
> 即使您沒有為組織啟用遠端使用者存取，您也可以設定原則來控制遠端使用者存取。 不過，您設定的原則只有當您為組織啟用遠端使用者存取時才會生效。 此外，如果您指定用來控制遠端使用者存取的使用者原則，此原則只適用于已啟用商務用 Skype 伺服器的使用者，且設定為使用原則。 如需指定可以從遠端位置登入商務用 Skype Server 之使用者的詳細資訊，請參閱 [指派外部使用者存取原則](assign-an-external-user-access-policy.md)。

使用下列程式可設定每個要用來控制遠端使用者存取的外部存取原則。


> [!NOTE]  
> 此程式說明如何設定原則，只啟用與遠端使用者的通訊，但設定為支援遠端使用者存取的每個原則也可以設定同盟使用者存取和公用使用者存取。 如需設定支援同盟使用者之原則的詳細資訊，請參閱 [在商務用 Skype Server 中設定原則以控制同盟使用者存取](configure-policies-to-control-federated-user-access.md)。 如需設定原則以支援公用使用者的詳細資訊，請參閱 [在商務用 Skype Server 中管理組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>設定外部存取原則以支援遠端使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 

3.  在左導覽列中，依序按一下 [外部使用者存取] 及 [外部存取原則]。

4.  在「外部存取原則」頁面中，執行下列其中一項：
    
      - 若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
      - 若要建立新的網站原則，請按一下 **[新增]**，然後按一下 **[站台原則]**。在 **[選取站台]** 的清單中按一下適當網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。 在 [ **新增外部存取原則**] 中，在 [ **名稱** ] 欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容 (例如，針對為遠端使用者) 啟用通訊的使用者原則，請 **EnableRemoteUsers** 。
    
      - 若要變更現有原則，按一下表中所列之適當原則，然後按一下 [編輯]，接著按一下 [顯示詳細資料]。

5.  (選用) 如果您想要新增或編輯說明，請在 [說明] 中指定原則資訊。

6.  執行下列其中一項作業：
    
      - 若要啟用原則的遠端使用者存取，請選取 [ **啟用與遠端使用者的通訊** ] 核取方塊。
    
      - 若要停用原則的遠端使用者存取，請清除 [ **啟用與遠端使用者的通訊** ] 核取方塊。

7.  按一下 **[認可]**。

若要啟用遠端使用者存取，您也必須啟用組織中遠端使用者存取的支援。 如需詳細資訊，請參閱 [Enable or disable federation and PUBLIC IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

如果這是使用者原則，您也必須將原則套用至您要能夠遠端連線的使用者。 如需詳細資訊，請參閱 [指派外部使用者存取原則](assign-an-external-user-access-policy.md)。
