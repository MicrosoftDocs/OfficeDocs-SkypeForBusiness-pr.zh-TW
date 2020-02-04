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
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 中遠端呼叫控制的部署工作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

本主題描述您必須執行才能針對 Lync Server 環境中的使用者啟用遠端通話控制的部署工作。

<div>


> [!NOTE]  
> 如果您在 Microsoft Office Communicator 2007 R2 中將先前已啟用遠端通話控制的使用者遷移，您必須先執行額外的部署工作，才能開始執行本主題中所述的遠端呼叫控制部署工作。 在將程式遷移至 Lync Server 時，必須視需要使用 Office 通訊伺服器 2007 R2 管理工具移除受信任的應用程式專案（先前稱為<EM>授權主項目目</EM>）。<BR>如需有關移除授權主機的詳細資訊，請參閱<A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中移除舊版授權主機（選用）</A>。



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>步驟1：安裝及設定 SIP/CSTA 閘道以與您的 PBX 進行通訊

您必須在您的環境中安裝至少一個能連線到 Lync Server 和現有私人分支 exchange （PBX）的 SIP/CSTA 閘道，以便為您的使用者提供遠端通話控制功能。 SIP/CSTA 閘道是 SIP 與電腦支援的電訊應用程式（CSTA）之間的閘道。 不論您是否安裝多個閘道或只有一個，每個使用者都可以使用一個閘道或 PBX 進行設定。 如果您的現有 PBX 沒有 SIP/CSTA 介面，請確保您部署可支援 PBX 的 SIP/CSTA 閘道，包括對專用 PBX 供應商特定的信號通訊協定的支援。 如需功能的詳細資訊，請直接向每個供應商諮詢。

當您準備好要部署可與 Lync Server 進行遠端通話控制的 SIP/CSTA 閘道時，請諮詢您的閘道廠商或供應商的閘道檔，瞭解閘道所需的語法，以及下列資訊：

  - 閘道的行伺服器 URI

  - 將指派給閘道之使用者的行 URI

上述設定是在使用者設定期間需要的，而且必須按照閘道的預期來指定，才能正確地路由及連線到 PBX。

您可以在 Microsoft 整合通訊開啟互通性計畫網站上，參閱[http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)提供給合作夥伴。

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>步驟2：將 Lync Server 設定為將 CSTA 要求傳送到 SIP/CSTA 閘道

您必須在您想要路由遠端通話控制要求之部署中的所有 SIP/CSTA 閘道的目的地位址（伺服器 URI），在 Lync 伺服器池中建立靜態路由。 您也必須建立對應至每個目的地位址的信任應用程式專案。 當您將閘道指派為受信任的應用程式時，它會被指定為在 Lync Server 環境中執行的信任狀態，即使是由協力廠商開發（並執行稱為*外部服務*的服務，因為它是產品的內建元件）。 最後，如果 Lync Server 會使用傳輸控制通訊協定（TCP）連線（而不是傳輸層安全性（TLS）連線）連線到 SIP/CSTA 閘道，您也必須使用拓撲結構建立程式來定義閘道 IP 位址。

如需設定靜態路由的詳細資料，請參閱[在 Lync Server 2013 中設定遠端通話控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。

如需設定受信任的應用程式專案的詳細資料，請參閱[在 Lync Server 2013 中設定遠端通話控制的信任應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。

如需在拓撲結構建立器中定義 SIP/CSTA 閘道 IP 位址的詳細資料，請參閱[在 Lync Server 2013 中定義 sip/CSTA 閘道 ip 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>步驟3：設定遠端通話控制的 Lync 使用者

在使用者啟用 Lync Server 之後，您可以使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面] 來啟用遠端通話控制。 在此部署步驟中，您可以為每位使用者指派線條伺服器 URI 和行 URI。 Line server URI 是您計畫指派給使用者的 SIP/CSTA 閘道的 SIP URI。 [行 URI] 是指派給使用者的唯一電話號碼。

如需針對遠端通話控制設定使用者的詳細資料，請參閱[在 Lync Server 2013 中啟用遠端通話控制的 Lync 使用者](lync-server-2013-enable-lync-users-for-remote-call-control.md)。

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>步驟4：定義 Lync Server Phone 編號正常化規則

在遠端通話控制案例中，Lync Server 會使用電話號碼正規化規則，將它從 SIP/CSTA 閘道收到的電話號碼轉換為. 164 格式。 電話號碼必須是這個標準格式，才能正常運作。 [遠端通話控制] 會使用您針對通訊錄服務電話號碼正規化所設定的相同電話號碼正規化規則，這與企業語音所用的電話號碼正規化規則不同。

如需遠端通話控制如何使用電話號碼正規化規則的詳細資料，請參閱[Lync Server 2013 中的遠端通話控制和電話號碼標準化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)。 如需通訊錄服務的電話號碼正規化規則的詳細資料，請參閱在作業檔中[管理 Lync Server 2013 主題中的通訊錄服務](lync-server-2013-administering-the-address-book-service.md)主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

