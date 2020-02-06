---
title: 管理組織的 SIP 同盟網域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: 瞭解如何管理及設定可與您聯盟的 SIP 網域，
ms.openlocfilehash: af014c6c24d3655612846e97cfa7ff5c7b9c816b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818234"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>在商務用 Skype Server 中管理貴組織的 SIP 聯盟網域


若要管理和設定可與您聯盟的 SIP 網域，您可以執行下列動作：

  - 建立或編輯 SIP 聯盟夥伴網域的允許網域清單。

  - 建立或編輯受封鎖之 SIP 聯盟網域的網域清單。

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>在商務用 Skype Server 中設定允許的外部網域支援

如果您已設定聯盟夥伴的支援，您可以管理哪些特定網域可以與您的組織聯盟。 您將一或多個特定外部網域設定為允許聯盟網域。 若要這樣做，請將每個網域新增到允許的網域清單中。 即使您的組織已啟用合作夥伴探索，如果網域是聯盟夥伴，可能需要與超過1000的使用者通訊，或者可能需要每秒傳送超過20封郵件。 如果您的組織未啟用合作夥伴探索，則只有您新增至 [允許的網域] 清單的外部網域使用者，才能與組織中的使用者參與 IM 和會議。 如果您想要將同盟網域的存取許可權制為執行同盟夥伴之存取邊緣服務的特定伺服器，您可以在允許的網域清單中，為每個網域指定執行 Access Edge 服務的伺服器功能變數名稱。

> [!NOTE]  
> 此程式說明如何針對特定網域設定支援，但實現同盟使用者的支援也需要您針對貴組織啟用聯盟使用者支援，以及設定及套用原則，以控制哪些使用者可以與聯盟使用者共同作業。 如需有關啟用聯盟使用者支援的詳細資料，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。 如需設定控制同盟的原則的詳細資料，請參閱[設定控制聯盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>將外部網域新增至允許的網域清單

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。
2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**聯盟網域**]。
4.  在 [**聯盟網域**] 頁面上，按一下 [**新增**]，然後按一下 [**允許的網域**]。
5.  在**新的聯盟網域**中，請執行下列動作：
    
      - 在 **[Domain name （或 FQDN）**] 中，輸入聯盟夥伴網域的名稱。       

        > [!NOTE]  
        > 這個名稱必須是唯一的，而且不能作為執行存取邊緣服務的此伺服器的允許網域存在。 名稱長度不能超過256個字元。<BR><br>在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。 例如，如果您輸入**contoso.com**，則搜尋也會傳回網域**it.contoso.com**。<BR><br>聯盟夥伴網域不能同時封鎖及允許。 商務用 Skype Server 無法避免這種情況，因此您不需要同步處理您的清單。
    
      - 如果您想要將此聯盟網域的存取許可權制為執行存取邊緣服務的特定伺服器的使用者，請在 **[存取邊緣服務（FQDN）**] 中，輸入執行 [存取邊緣] 服務之聯盟網域伺服器的 FQDN。    
      - 如果您想要提供其他資訊，請在 [**批註**] 中，輸入您要與其他系統管理員共用此設定的資訊。

6.  按一下 [認可]****。
7.  針對您要允許的每個聯盟夥伴網域，重複步驟4到6。

若要啟用同盟使用者存取，您也必須在組織中啟用聯盟使用者存取的支援。 如需詳細資訊，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。

此外，您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱[設定控制聯盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>在商務用 Skype Server 中設定封鎖的外部網域支援 

如果您已設定聯盟夥伴的支援，您可以管理哪些網域將被封鎖，無法與您的組織進行聯盟。 封鎖的網域清單會充當封鎖清單（不允許的明確專案清單），如果您已啟用此選項，就會套用到聯盟網域探索中。 如需詳細資訊，請參閱[啟用或停用同盟合作夥伴的探索](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。

封鎖一或多個外部網域以連線到您的組織。 若要這樣做，請將網域新增到封鎖網域的清單中。


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>將外部網域新增至封鎖的網域清單

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。
2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3.  在左側導覽列中，按一下 [**外部使用者存取**]。
4.  按一下 [**聯盟網域**]，按一下 [**新增**]，然後按一下 [**封鎖的網域**]。
5.  在**新的聯盟網域**中，請執行下列動作：
    
      - 在 **[Domain name （或 FQDN）**] 中，輸入您要封鎖的聯盟夥伴網域的名稱。

        > [!NOTE]  
        > 名稱長度不能超過256個字元。<BR><br>在聯盟夥伴網功能變數名稱稱上的搜尋會執行尾碼相符。 例如，如果您輸入**contoso.com**，則搜尋也會傳回網域**it.contoso.com**。<BR><br>聯盟夥伴網域不能同時封鎖及允許。 商務用 Skype Server 無法避免這種情況，因此您不需要同步處理您的清單。
   
      - 可選在 [**批註**] 中，輸入您要與其他系統管理員共用這項設定的資訊。

6.  按一下 [認可]****。
7.  針對您要封鎖的每個聯盟夥伴，重複步驟4到6。

若要啟用同盟使用者存取，您也必須在組織中啟用聯盟使用者存取的支援。 如需詳細資訊，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。

此外，您必須設定並將原則套用到您想要能夠與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱[設定控制聯盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)。


## <a name="see-also"></a>請參閱

[設定控制同盟使用者存取的原則](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[啟用或停用同盟和公用 IM 連線](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[啟用或停用同盟協力廠商探索](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

