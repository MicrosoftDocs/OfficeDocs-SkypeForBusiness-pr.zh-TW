---
title: 設定內部部署 Lync Server 與 Exchange Online 整合
description: 設定內部部署 Lync Server 與 Exchange Online 整合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c612bcdcdf4803bd6f9f2b38f1f9bb7dbad016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553932"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>設定內部部署 Lync Server 2013 與 Exchange Online 整合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018-03-30_

使用內部部署 Lync Server 2013 部署的客戶可以在混合式部署模式中，設定 microsoft Exchange Online 中 Microsoft Outlook Web App 的互通性。 互通性功能包括單一登入和立即訊息 (IM) 和目前狀態與 Outlook Web App 介面的整合。 若要啟用此整合，您必須完成下列工作，以在您的內部部署 Lync Server 部署中設定 Edge Server：

  - 設定共用 SIP 位址空間

  - 在 Edge Server 上設定裝載提供者

  - 驗證更新的中央管理存放區複寫

如果 Lync Server 2013 與 Exchange Online 整合，嘗試從 OWA 登入 IM 的使用者被視為遠端或外部使用者。 在此案例中，此使用者必須已被指派具有下列選項的外部存取原則：

**啟用與遠端使用者的通訊**

如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）可以透過網際網路連線至 Lync Server，請啟用此選項。

如需詳細資訊，請參閱 [Manage external access policy In Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)。

<div>

## <a name="configure-a-shared-sip-address-space"></a>設定共用 SIP 位址空間

若要將內部部署的 Lync Server 2013 與 Exchange Online 整合，您必須設定共用 SIP 位址空間。 Lync Server 和 Exchange Online 服務都支援相同的 SIP 網域位址空間。

使用 Lync Server 管理命令介面，使用下列範例所示的參數執行 **Set-CSAccessEdgeConfiguration** Cmdlet，以設定 Edge server 以進行同盟：

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** 指定是否允許內部使用者與同盟網域的使用者進行通訊。 此屬性也會判斷內部使用者是否可以使用 Lync Server 和 Exchange Online，與共享 SIP 位址空間案例中的使用者進行通訊。

如需如何使用 Lync Server 管理命令介面的詳細資訊，請參閱 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在 Edge Server 上設定裝載提供者

使用 Lync Server 管理命令介面，在 Edge Server 上設定裝載提供者。 若要這麼做，請使用下列範例中的參數執行 **New-CsHostingProvider** Cmdlet：

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> 如果您使用的是在中國運作的 Office 365，請將此範例中的 <STRONG>ProxyFqdn</STRONG> 參數值取代為世紀所運作之服務的 FQDN ( "exap.um.outlook.com" ) ： "exap.um.partner.outlook.cn"。



</div>

  - **Identity** 為您要建立的裝載提供者指定唯一的字串值識別碼 (例如「Exchange Online」 ) 。 包含空格的值必須用雙引號括住。

  - **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。 這必須設定為 **True**。

  - **EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。 這必須設定為 **True**。

  - **HostsOCSUsers** 會指出裝載提供者是否是用來主控 Office 通訊伺服器或 Lync server。 這必須設定為 **False**。

  - **ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。 針對 Exchange Online，FQDN 是 exap.um.outlook.com。

  - **IsLocal** 指出主控提供者所使用的 proxy 伺服器是否包含在 Lync server 拓撲中。 這必須設定為 **False**。

  - **VerificationLevel** 表示所傳送的郵件所允許的驗證層級提供者。 指定 **UseSourceVerification**。 此選項取決於從裝載提供者傳送的郵件中所包含的驗證層級。 若未指定此層級，郵件將被拒絕為無法驗證。

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>驗證更新的中央管理存放區複寫

您使用上述各節中的 Cmdlet 所做的變更，會自動套用至 Edge Server，而且通常會在一分鐘內進行複製。 您可以使用下列 Cmdlet 來驗證複寫狀態，以及是否已將變更套用至 Edge Server。

若要驗證 Lync Server 部署中內部伺服器的複寫更新，請執行下列 Cmdlet：

    Get-CsManagementStoreReplicationStatus

若要確認是否已套用變更，請在 Edge Server 上執行下列 Cmdlet：

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>另請參閱


[在主控 Exchange UM 上提供 Lync Server 2013 使用者語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013 中的主控 Exchange 整合通訊整合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
