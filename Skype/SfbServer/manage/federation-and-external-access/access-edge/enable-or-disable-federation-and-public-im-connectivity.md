---
title: 啟用或停用同盟和公用 IM 連線
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: 必須具備同盟的支援，才能讓具有信任之客戶或夥伴組織之帳戶的使用者（包括夥伴網域和公用立即訊息 (IM) 提供者使用者）與組織中的使用者共同作業。
ms.openlocfilehash: f9c7b4ee7a861bc395c8599283f8d993b25ef4774d9487263e334207e9e277c8
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849968"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>啟用或停用商務用 Skype Server 中的同盟和公用 IM 連線

必須具備同盟的支援，才能讓具有信任之客戶或夥伴組織之帳戶的使用者（包括夥伴網域和公用立即訊息 (IM) 提供者使用者）與組織中的使用者共同作業。 同盟也是使用主控的 Exchange 服務供應商來提供語音信箱給企業語音使用者的使用者，這些使用者的信箱位於主控 Exchange 服務上，例如 Microsoft Exchange Online。 當您建立與這些外部網域的信任關係後，您可以授權這些網域中的使用者存取您的部署，並參與商務用 Skype Server 通訊。 此信任關係稱為同盟，它與 Active Directory 信任關聯或無關。

若要支援同盟網域使用者的存取，您必須啟用同盟。 如果您為組織啟用同盟，您也必須指定是否要執行下列選項：

  - **啟用夥伴網域探索**  如果您啟用此選項，商務用 Skype Server 會使用網域名稱系統 (DNS) 記錄，以嘗試找出未列在 [允許的網域] 清單中的網域、自動評估已發現同盟夥伴的內送流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。 如果您未選取此選項，則只有您在允許的網域清單上所包含之網域中的使用者啟用同盟使用者存取。 不論是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制存取同盟網域中的 Access Edge service 的特定伺服器。 如需如何透過同盟網域來控制存取的詳細資訊，請參閱 [Configure support for 允許的外部網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。

  - **將封存免責聲明傳送給同盟夥伴**    免責聲明通知會傳送給同盟協力廠商，以在您的部署中進行封存。 如果您支援與同盟協力廠商網域的外部通訊封存，您應該啟用封存免責聲明通知，以警告協力廠商郵件正在封存。

如果您稍後想要暫時或永久防止同盟網域的使用者進行存取，您可以停用組織的同盟。 使用本節中的程式來啟用或停用組織的同盟使用者存取，包括指定您的組織支援的適當同盟選項。

> [!NOTE]  
> 為您的組織啟用同盟，只會指定執行 Access Edge service 的伺服器支援路由傳送至同盟網域。 除非您也設定至少一個原則以支援同盟使用者存取，否則同盟網域中的使用者無法參與您組織中的 IM 或會議。 公用 IM 服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您也設定至少一個原則來支援公用 IM 連線。 商務用 Skype Server 無法使用主控 Exchange 服務提供呼叫回應、Outlook 語音存取 (包括語音信箱) 或自動語音應答服務，以供信箱位於主控 Exchange 服務上的使用者，直到您設定可提供路由資訊的主控語音信箱原則為止。 如需設定策略以與其他組織中同盟網域的使用者進行通訊的詳細資訊，請參閱 [管理組織的 SIP 同盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。 此外，如果您想要支援與 IM 服務提供者的使用者進行通訊，則必須設定原則來支援它，也為您要支援的個別服務提供者設定支援。 如需詳細資訊，請參閱   [管理組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>啟用或停用組織的同盟使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge** 設定]。

4.  在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯 Access Edge** 設定] 中，執行下列其中一項操作：
    
      - 若要啟用組織的同盟使用者存取，請選取 [ **啟用與同盟使用者的通訊** ] 核取方塊。
    
      - 若要停用組織的同盟使用者存取，請清除 [ **啟用與同盟使用者的通訊** ] 核取方塊。

6.  如果您選取 [ **啟用與同盟使用者的通訊** ] 核取方塊，請執行下列操作：
    
    1.  如果您想要支援自動探索夥伴網域，請選取 [ **啟用夥伴網域探索** ] 核取方塊。
    
    2.  如果您的組織支援外部通訊的封存，請選取 [將封存 **免責聲明傳送給同盟夥伴** ] 核取方塊。

7.  按一下 **[認可]**。

若要讓同盟使用者能夠與您的商務用 Skype Server 部署中的使用者共同作業，您也必須設定至少一個外部存取原則，以支援同盟使用者存取。 如需詳細資訊，請參閱 [設定原則以控制同盟使用者存取](../external-access-policies/configure-policies-to-control-federated-user-access.md)。 若要控制特定同盟網域的存取權，請參閱 [Configure support for 允許的外部網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用同盟與公用 IM 連線

同盟和公用 IM 連線能力也可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>啟用同盟和公用 IM 連線

  - 若要啟用同盟和公用 IM 連線，請將 **AllowFederatedUsers** 屬性的值設為 True ($True) ：<br/><br/>Set-CsAccessEdgeConfiguration-AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>停用同盟和公用 IM 連線

  - 若要停用同盟和公用 IM 連線，請將 **AllowFederatedUsers** 屬性的值設為 False ($False) ：<br/><br/>Set-CsAccessEdgeConfiguration-AllowFederatedUsers $False

