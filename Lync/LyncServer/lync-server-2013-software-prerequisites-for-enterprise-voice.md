---
title: Lync Server 2013：Enterprise Voice 的軟體先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="6ed40-102">Lync Server 2013 中 Enterprise Voice 的軟體先決條件</span><span class="sxs-lookup"><span data-stu-id="6ed40-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ed40-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6ed40-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6ed40-104">確認您要部署企業語音的基礎結構符合下列軟體先決條件：</span><span class="sxs-lookup"><span data-stu-id="6ed40-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="6ed40-105">Lync Server 2013 標準版或 Enterprise Edition 已安裝並在您的網路上運作。</span><span class="sxs-lookup"><span data-stu-id="6ed40-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="6ed40-106">所有邊緣伺服器都是在您的周邊網路中部署和執行，包括執行存取邊緣服務的邊緣伺服器、A/V 邊緣服務、網頁會議 Edge 服務，以及反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="6ed40-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="6ed40-107">您可以使用 Microsoft Exchange Server 2007 Service Pack 3 （SP3）、Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013，以與 Lync Server 整合 Exchange 整合訊息，並提供豐富的通知及通話記錄資訊給Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="6ed40-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="6ed40-108">已為 Lync Server 建立並啟用一或多位使用者。</span><span class="sxs-lookup"><span data-stu-id="6ed40-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="6ed40-109">已成功部署 Lync 用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="6ed40-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="6ed40-110">拓撲建立程式已安裝在您網路上的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="6ed40-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="6ed40-111">後續步驟：驗證安全性與設定先決條件</span><span class="sxs-lookup"><span data-stu-id="6ed40-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="6ed40-112">驗證企業語音的軟體先決條件之後，您可以使用檔來繼續準備部署企業語音：</span><span class="sxs-lookup"><span data-stu-id="6ed40-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="6ed40-113">驗證安全性、使用者設定和硬體 perquisites，如在[Lync Server 2013 的安全性和設定先決條件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="6ed40-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="6ed40-114">安裝中繼伺服器，如在[Lync server 2013 中安裝用於進行轉送服務伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中所述，但*僅限*您想要部署獨立的中繼伺服器或池，因為在 collocated 時，會將轉送伺服器安裝為前端池或標準版伺服器部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6ed40-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="6ed40-115">設定幹線連線為使用者提供 PSTN 連線，如在[Lync Server 2013 中設定 trunks 中](lync-server-2013-configuring-trunks.md)所述。</span><span class="sxs-lookup"><span data-stu-id="6ed40-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

