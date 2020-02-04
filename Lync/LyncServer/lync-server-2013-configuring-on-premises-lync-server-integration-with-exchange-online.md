---
title: 配置與 Exchange Online 的內部部署 Lync Server 整合
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
ms.openlocfilehash: a652fea6c54592526047e8d8b35a0bddd0ef1995
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>配置與 Exchange Online 的內部部署 Lync Server 2013 整合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018-03-30_

使用內部部署 Lync Server 2013 部署的客戶可以在混合式部署模式中，以 Microsoft Exchange Online 中的 Microsoft Outlook Web App 來設定互通性。 互通性功能包括單一登入與立即訊息（IM），以及與 Outlook Web App 介面的目前狀態整合。 若要啟用此整合，您必須完成下列工作，才能在您的內部部署 Lync Server 部署中設定 Edge 伺服器：

  - 設定共用的 SIP 位址空間

  - 在 Edge 伺服器上設定主機服務提供者

  - 驗證已更新的中央管理存放區的複製

如果 Lync Server 2013 已與 Exchange Online 整合，嘗試從 OWA 登入 IM 的使用者會被視為遠端或外部使用者。 在此案例中，此使用者必須已指派外部存取原則，且已選取下列選項：

**啟用與遠端使用者的通訊**

如果您想讓組織外部的使用者（例如出差的遠端電腦）能夠透過網際網路連線至 Lync Server，請啟用此選項。

如需詳細資訊，請參閱[在 Lync Server 2013 中管理外部存取原則](lync-server-2013-manage-external-access-policy-for-your-organization.md)。

<div>

## <a name="configure-a-shared-sip-address-space"></a>設定共用的 SIP 位址空間

若要將內部部署的 Lync Server 2013 與 Exchange Online 整合在一起，您必須設定共用的 SIP 位址空間。 Lync Server 和 Exchange Online 服務都支援相同的 SIP 網域位址空間。

使用 Lync Server 管理命令介面，透過執行**CSAccessEdgeConfiguration** Cmdlet 來設定聯盟的邊緣伺服器，方法是使用下列範例中顯示的參數：

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers ** 指定是否允許內部使用者與同盟網域的使用者進行通訊。 這個屬性也會判斷內部使用者是否可使用 Lync Server 和 Exchange Online 與共享 SIP 位址空間案例中的使用者進行通訊。

如需有關如何使用 Lync Server 管理命令介面的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在 Edge 伺服器上設定主機服務提供者

使用 Lync Server 管理命令介面，在 Edge 伺服器上設定主機服務提供者。 若要這樣做，請使用下列範例中的參數來執行**新的 CsHostingProvider** Cmdlet：

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> 如果您使用的是中國由世紀運營的 Office 365，請將此範例（"exap.um.outlook.com"）中<STRONG>ProxyFqdn</STRONG>參數的值，以由世紀運營的服務 FQDN 取代（"exap.um.partner.outlook.cn"）。



</div>

  - 身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼（例如，「Exchange Online」）。 包含空格的值必須以雙引號括住。

  - **Enabled ** 指出網域與裝載提供者之間的網路連線是否已啟用。 這必須設定為**True**。

  - **EnabledSharedAddressSpace**表示主機服務提供者是否將用於共用的 SIP 位址空間案例中。 這必須設定為**True**。

  - **HostsOCSUsers**表示主機服務提供者是否是用來託管 Office 通訊伺服器或 Lync server。 必須將它設為**False**。

  - **ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱（FQDN）。 針對 Exchange Online，FQDN 是 exap.um.outlook.com。

  - **IsLocal** ：指示主機服務提供者所使用的 proxy 伺服器是否包含在您的 Lync server 拓撲中。 必須將它設為**False**。

  - **VerificationLevel**表示傳送到託管提供者的郵件所允許的驗證等級。 指定**UseSourceVerification**。 這個選項依賴于從主機服務提供者傳送的訊息中所包含的驗證層級。 如果未指定此等級，郵件將會因無法驗證而遭到拒絕。

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>驗證已更新的中央管理存放區的複製

您使用上述章節中的 Cmdlet 所做的變更，會自動套用至 Edge 伺服器，且通常需要不到一分鐘的時間來複製。 您可以使用下列 Cmdlet 來驗證複製狀態，以及所做的變更已套用至 Edge 伺服器。

若要在 Lync Server 部署的內部伺服器上驗證複製更新，請執行下列 Cmdlet：

    Get-CsManagementStoreReplicationStatus

若要確認已套用所做的變更，請在 Edge 伺服器上執行下列 Cmdlet：

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>請參閱


[在主控 Exchange UM 上提供 Lync Server 2013 使用者語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013 中的主控 Exchange 整合通訊整合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

