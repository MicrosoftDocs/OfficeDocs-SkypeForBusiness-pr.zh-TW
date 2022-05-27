---
title: 啟用或停用同盟和公用 IM 連線
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 需要支援同盟，才能讓具有受信任客戶或合作夥伴組織帳戶的使用者，包括合作夥伴網域和公用立即訊息 (IM) 提供者使用者的使用者，與您組織中的使用者共同作業。
ms.openlocfilehash: 0b78eacd473422c204f8614464b406657f3dc92b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675745"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>在 商務用 Skype Server 中啟用或停用同盟和公用 IM 連線

需要支援同盟，才能讓具有受信任客戶或合作夥伴組織帳戶的使用者，包括合作夥伴網域和公用立即訊息 (IM) 提供者使用者的使用者，與您組織中的使用者共同作業。 使用託管Exchange服務提供者也需要同盟，才能為信箱位於託管Exchange服務上的企業語音使用者提供語音信箱，例如 Microsoft Exchange Online。 當您與這些外部網域建立信任關係時，您可以授權這些網域中的使用者存取您的部署，並參與商務用 Skype Server通訊。 此信任關係稱為同盟，與 Active Directory 信任關係無關或相依。

若要支援同盟網域使用者的存取，您必須啟用同盟。 如果您為組織啟用同盟，也必須指定是否要實作下列選項：

  - **啟用合作夥伴網域探索**  如果您啟用此選項，商務用 Skype Server會使用網域名稱系統 (DNS) 記錄，嘗試探索未列在允許網域清單中的網域、自動評估來自探索到同盟夥伴的連入流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。 如果您未選取此選項，同盟使用者存取只會針對您包含在允許網域清單上的網域中的使用者啟用。 無論您是否選取此選項，都可以指定要封鎖或允許的個別網域，包括限制對在同盟網域中執行 Access Edge 服務的特定伺服器的存取。 如需控制同盟網域存取權的詳細資訊，請參閱設定 [對允許外部網域的支援](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。

  - **將封存免責聲明傳送給同盟合作夥伴**    免責聲明會傳送給已在部署中封存的同盟合作夥伴。 如果您支援封存與同盟夥伴網域的外部通訊，您應該啟用封存免責聲明通知，以警告合作夥伴其訊息已封存。

如果您稍後想要暫時或永久防止同盟網域的使用者存取，您可以停用組織的同盟。 使用本節中的程式來啟用或停用組織的同盟使用者存取，包括指定要為組織支援的適當同盟選項。

> [!NOTE]  
> 為您的組織啟用同盟只會指定執行 Access Edge 服務的伺服器支援路由傳送至同盟網域。 在您也設定至少一個原則來支援同盟使用者存取之前，同盟網域中的使用者無法參與組織中的 IM 或會議。 公用 IM 服務提供者的使用者無法參與組織中的 IM 或會議，直到您也設定至少一個原則來支援公用 IM 連線。 商務用 Skype Server在您設定提供路由資訊的託管語音信箱原則之前 Outlook 語音存取 (，商務用 Skype Server無法使用託管的Exchange服務，為信箱位於託管Exchange服務的使用者提供語音信箱) 或自動語音應答服務。 如需設定原則以與其他組織中同盟網域使用者通訊的詳細資訊，請參閱 [管理組織的 SIP 同盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。 此外，如果您想要支援與 IM 服務提供者的使用者通訊，您必須設定原則來支援它，同時也要為您想要支援的個別服務提供者設定支援。 如需詳細資訊，請   [參閱管理組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>為您的組織啟用或停用同盟使用者存取

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶， (或具有對等的使用者權限) ，或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理員 URL 以開啟商務用 Skype Server 主控台。 

3.  在左側導覽列中，按一下 [ **外部使用者存取]**，然後按一下 [ **Access Edge 設定]**。

4.  在 [ **Access Edge 組態]** 頁面上，依序按一下 [ **全域**]、[ **編輯**] 及 [ **顯示詳細資料]**。

5.  在 **[編輯存取 Edge 設定**] 中，執行下列其中一項：
    
      - 若要為您的組織啟用同盟使用者存取權，請選取 [ **啟用與同盟使用者的通訊** ] 核取方塊。
    
      - 若要停用組織的同盟使用者存取，請清除 [ **啟用與同盟使用者的通訊** ] 核取方塊。

6.  如果您選取 [ **啟用與同盟使用者的通訊** ] 核取方塊，請執行下列動作：
    
    1.  如果您想要支援自動探索合作夥伴網域，請選取 [ **啟用合作夥伴網域探索** ] 核取方塊。
    
    2.  如果您的組織支援封存外部通訊，請選取 [將 **封存免責聲明傳送給同盟夥伴** ] 核取方塊。

7.  按一下 **[認可]**。

若要讓同盟使用者能夠與商務用 Skype Server部署中的使用者共同作業，您也必須設定至少一個外部存取原則，以支援同盟使用者存取。 如需詳細資訊，[請參閱設定原則以控制同盟使用者存取。](../external-access-policies/configure-policies-to-control-federated-user-access.md) 若要控制特定同盟網域的存取權， [請參閱設定對允許外部網域的支援](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用或停用同盟和公用 IM 連線

同盟和公用 IM 連線也可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。 此 Cmdlet 可以從商務用 Skype Server管理命令介面或從Windows PowerShell的遠端會話執行。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>啟用同盟和公用 IM 連線

  - 若要啟用同盟和公用 IM 連線，請將 **AllowFederatedUsers** 屬性的值設定為 True ($True) ：<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>停用同盟和公用 IM 連線

  - 若要停用同盟和公用 IM 連線，請將 **AllowFederatedUsers** 屬性的值設定為 False ($False) ：<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

