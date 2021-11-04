---
title: 管理貴組織的 SIP 同盟網域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: 瞭解如何管理及設定您可以同盟的 SIP 網域，
ms.openlocfilehash: 455cac695ead7f073269fe3df0e70ea5b26ccb0e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743539"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>在商務用 Skype Server 中管理組織的 SIP 同盟網域


若要管理及設定您可以同盟的 SIP 網域，您可以執行下列作業：

  - 建立或編輯 SIP 同盟協力廠商網域的允許網域清單。

  - 建立或編輯 SIP 同盟網域的封鎖網域清單。

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>為商務用 Skype Server 中的允許外部網域設定支援

如果已設定對同盟協力廠商的支援，則可以管理哪些特定網域可以與您的組織進行同盟。設定一個或多個特定的外部網域作為允許的同盟網域。若要這樣做，請將每個所需網域新增至允許網域清單。如果網域是可能需要與您超過 1,000 位使用者通訊或每秒傳送超過 20 封訊息的同盟協力廠商，則即使您的組織已啟用協力廠商探索，也建議您這樣做。如果您的組織未啟用協力廠商探索，則只有已新增至允許網域清單的外部網域的使用者，才能和您組織內的使用者進行 IM 和會議通訊。如果您要將同盟網域的存取限制於同盟協力廠商執行 Access Edge Service 的特定伺服器，可以針對允許網域清單中的每個網域，指定執行 Access Edge Service 之伺服器的網域名稱。

> [!NOTE]  
> 此程序說明如何設定特定網域的支援，但實作同盟使用者的支援還需要您的組織啟用同盟使用者的支援，以及設定和套用原則以控制哪些使用者可以與同盟使用者共同作業。 如需啟用同盟使用者支援的詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。 如需設定控制同盟之原則的詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>若要將外部網域新增至允許網域清單

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。
2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3.  在左導覽列中，依序按一下 **[外部使用者存取]** 和 **[同盟網域]**。
4.  在 **[同盟網域]** 頁面上，依序按一下 **[新增]** 和 **[允許的網域]**。
5.  在 **[新增同盟網域]** 中，執行下列動作：
    
      - 在 **[網域名稱 (或 FQDN)]** 中，輸入同盟協力廠商網域的名稱。       

        > [!NOTE]  
        > 此名稱必須是唯一的，而且不能已存在作為這個執行 Access Edge Service 的伺服器的允許網域。此外，名稱長度不可超過 256 個字元。<BR><br>搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 **contoso.com**，搜尋也會傳回網域 **it.contoso.com**。<BR><br>不能同時封鎖又允許同一個同盟協力廠商網域。 商務用 Skype Server 避免發生這種情況，所以您不需要同步處理清單。
    
      - 如果您要將同盟網域的存取限制於執行 Access Edge Service 之特定伺服器的使用者，可以在 **[Access Edge Service (FQDN)]** 中輸入執行 Access Edge Service 之同盟網域伺服器的 FQDN。    
      - 如果您要提供其他資訊，請在 **[註解]** 中輸入您想與其他系統管理員分享有關此設定的資訊。

6.  按一下 **[認可]**。
7.  為您要允許的每個同盟協力廠商網域重複步驟 4 到 6。

若要啟用同盟使用者存取，您也必須在組織中啟用對同盟使用者存取的支援。 如需詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。

此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>在商務用 Skype Server 中為封鎖的外部網域設定支援 

如果您已設定同盟協力廠商的支援，可以管理要禁止哪些網域與您的組織建立同盟。 如果您啟用此選項，封鎖網域清單將作為封鎖清單 (不被允許的明確項目清單)，並套用於同盟網域探索中。 如需詳細資訊，請參閱 [啟用或停用同盟](../access-edge/enable-or-disable-discovery-of-federation-partners.md)協力廠商的探索。

封鎖一個或多個外部網域，不讓它們連線至您的組織。若要這樣做，請將網域新增至封鎖網域清單。


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>將外部網域新增至封鎖網域清單

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。
2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3.  在左導覽列中，按一下 **[外部使用者存取]**。
4.  依序按一下 **[同盟網域]**、**[新增]** 和 **[封鎖網域]**。
5.  在 **[新增同盟網域]** 中，執行下列動作：
    
      - 在 **[網域名稱 (或 FQDN)]** 中，輸入您要封鎖的同盟協力廠商網域名稱。

        > [!NOTE]  
        > 名稱長度不可超過 256 個字元。<BR><br>搜尋同盟協力廠商網域名稱時會執行尾碼比對。例如，如果輸入 **contoso.com**，搜尋也會傳回網域 **it.contoso.com**。<BR><br>不能同時封鎖又允許同一個同盟協力廠商網域。 商務用 Skype Server 避免發生這種情況，所以您不需要同步處理清單。
   
      - (選用) 在 **[註解]** 中，輸入您想與其他系統管理員分享的此設定相關資訊。

6.  按一下 **[認可]**。
7.  為您要封鎖的每個同盟協力廠商重複步驟 4 到 6。

若要啟用同盟使用者存取，您也必須在組織中啟用同盟使用者存取支援。 如需詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。

此外，您還必須設定原則，並將原則套用至您希望能與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。


## <a name="see-also"></a>另請參閱

[設定控制同盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[啟用或停用同盟和公用 IM 連線](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[啟用或停用同盟協力廠商探索](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

