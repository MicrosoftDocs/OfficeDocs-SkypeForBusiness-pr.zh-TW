---
title: Lync Server 2013：遠端呼叫控制的部署工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2ac45e0f589ac155d2e0f51b0115036a97809e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499050"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 中遠端呼叫控制的部署工作

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

本主題說明為您的 Lync Server 環境中的使用者啟用遠端呼叫控制時必須執行的部署工作。

<div>


> [!NOTE]  
> 如果您要在 Microsoft Office Communicator 2007 R2 中遷移先前為遠端呼叫控制啟用的使用者，您必須先執行額外的部署工作，再開始執行本主題中所述的遠端呼叫控制部署工作。 在將遷移程式移至 Lync Server 時，已 (先前稱為 <EM>授權主項目目</EM> 的受信任應用程式專案) ，必須視需要使用 Office 通訊伺服器 2007 R2 系統管理工具加以移除。<BR>如需移除授權主機的詳細資訊，請參閱 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a 舊版授權主機 In Lync Server 2013 (選用) </A>。



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>步驟1：安裝並設定 SIP/CSTA 閘道與 PBX 通訊

您必須在您的環境中至少安裝一個可同時連接至 Lync Server 與現有私人分支 exchange (PBX) 的 SIP/CSTA 閘道，以便為您的使用者提供遠端呼叫控制功能。 SIP/CSTA 閘道是 SIP 和電腦支援之電信應用程式 (CSTA) 之間的閘道。 不論您是安裝多個閘道，還是只安裝一個閘道，每一位使用者都可以設定一個閘道或 PBX。 如果現有的 PBX 沒有 SIP/CSTA 介面，請確定您部署可支援 PBX 的 SIP/CSTA 閘道，包括對專屬 PBX 廠商特有的信號通訊協定的支援。 如需功能的詳細資訊，請直接向每個廠商諮詢。

當您準備好部署可以與 Lync Server 整合以進行遠端呼叫控制的 SIP/CSTA 閘道時，請與您的閘道廠商或供應商的閘道檔，瞭解下列資訊的閘道所需之語法：

  - 閘道的行伺服器 URI

  - 將指派給閘道之使用者的行 URI

上述設定是在使用者設定期間需要的，且必須依閘道所期望的方式，以路由傳送並正確連接至 PBX。

您可以在 Microsoft 整合通訊開啟互通性計畫網站上，參閱廠商 [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) 。

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>步驟2：設定 Lync Server 將 CSTA 要求路由傳送至 SIP/CSTA 閘道

您必須在 Lync 伺服器集區上建立靜態路由，使其為您要路由傳送遠端呼叫控制要求之所有 SIP/CSTA 閘道的目的地位址 (Server URI) 。 您也必須建立對應于每個目的地位址的受信任應用程式專案。 當您將閘道指定為信任的應用程式時，它會被提供信任的狀態，以作為 Lync Server 環境的一部分來執行，即使它是由第三 (方開發，也會執行稱為 *外部服務* 的服務，因為它並非產品) 內建的元件。 最後，如果 Lync Server 會使用傳輸控制通訊協定 (TCP) 連線來連線至 SIP/CSTA 閘道，而不是傳輸層安全性 (TLS) 連線，您也必須使用拓撲產生器來定義閘道 IP 位址。

如需設定靜態路由的詳細資訊，請參閱 [在 Lync Server 2013 中設定遠端呼叫控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。

如需設定信任的應用程式專案的詳細資訊，請參閱 [在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。

如需在拓撲產生器中定義 SIP/CSTA 閘道 IP 位址的詳細資訊，請參閱 [在 Lync Server 2013 中定義 SIP/CSTA 閘道 ip 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>步驟3：設定 Lync 使用者進行遠端呼叫控制

啟用 Lync Server 的使用者之後，您可以使用 Lync Server 控制台或 Lync Server 管理命令介面來啟用遠端呼叫控制。 在此部署步驟中，您會為每位使用者指派行伺服器 URI 和行 URI。 Line server URI 是您計畫指派給使用者的 SIP/CSTA 閘道的 SIP URI。 行 URI 是指派給使用者的唯一電話號碼。

如需有關為遠端呼叫控制設定使用者的詳細資訊，請參閱 [在 Lync Server 2013 中啟用遠端呼叫控制的 Lync 使用者](lync-server-2013-enable-lync-users-for-remote-call-control.md)。

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>步驟4：定義 Lync Server 電話號碼正規化規則

在遠端呼叫控制案例中，Lync Server 會使用電話號碼正規化規則，將從 SIP/CSTA 閘道收到的電話號碼轉換成 e.164 格式。 電話號碼必須採用此標準化格式，特定的遠端呼叫控制功能才能正常運作。 遠端呼叫控制使用與您為通訊錄服務電話號碼正規化所設定的相同電話號碼正規化規則，這與用於 Enterprise Voice 的電話號碼正常化規則不同。

如需遠端呼叫控制如何使用電話號碼正規化規則的詳細資訊，請參閱 [Lync Server 2013 中的遠端呼叫控制和電話號碼](lync-server-2013-remote-call-control-and-phone-number-normalization.md)正規化。 如需通訊錄服務之電話號碼正規化規則的詳細資訊，請參閱 Operations 檔中的 [管理 Lync Server 2013 主題中的通訊錄服務](lync-server-2013-administering-the-address-book-service.md) 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

