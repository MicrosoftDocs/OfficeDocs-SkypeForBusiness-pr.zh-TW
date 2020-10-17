---
title: Lync Server 2013： Enterprise Voice 的軟體必要條件
description: Lync Server 2013： Enterprise Voice 的軟體必要條件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23d21f40e275431f0384448341aa25ecb628ebf9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558969"
---
# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="18f70-103">Lync Server 2013 中的 Enterprise Voice 的軟體必要條件</span><span class="sxs-lookup"><span data-stu-id="18f70-103">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18f70-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="18f70-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="18f70-105">確認您想要部署 Enterprise Voice 的基礎結構符合下列軟體先決條件：</span><span class="sxs-lookup"><span data-stu-id="18f70-105">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="18f70-106">Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且可在您的網路上運作。</span><span class="sxs-lookup"><span data-stu-id="18f70-106">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="18f70-107">所有 Edge Server 都會在周邊網路中部署及運作，包括執行 Access Edge service 的 Edge Server、A/V Edge service、Web 會議 Edge service 及反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="18f70-107">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="18f70-108">Microsoft Exchange Server 2007 Service Pack 3 (SP3) ，則需要 Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013，才能整合 Exchange 整合通訊與 Lync Server，並將豐富通知及通話記錄資訊提供給 Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="18f70-108">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="18f70-109">有一或多個使用者已建立並啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="18f70-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="18f70-110">已成功部署 Lync 用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="18f70-110">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="18f70-111">拓撲產生器是安裝在網路上的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="18f70-111">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="18f70-112">後續步驟：確認安全性和設定先決條件</span><span class="sxs-lookup"><span data-stu-id="18f70-112">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="18f70-113">確認 Enterprise Voice 的軟體先決條件後，您可以參考文件說明，繼續準備部署 Enterprise Voice：</span><span class="sxs-lookup"><span data-stu-id="18f70-113">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="18f70-114">依照 [Lync Server 2013 的安全性和設定先決條件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述，驗證安全性、使用者設定和硬體 perquisites。</span><span class="sxs-lookup"><span data-stu-id="18f70-114">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="18f70-115">如在 [Lync server 2013 中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案所述，安裝轉送伺服器，但 *只有* 在您想要部署獨立轉送伺服器或集區時，因為在組合時已將轉送伺服器安裝為前端集區或 Standard Edition Server 部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="18f70-115">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="18f70-116">設定主幹連線以為使用者提供 PSTN 連線能力，如在 [Lync Server 2013 中設定主幹中](lync-server-2013-configuring-trunks.md)所述。</span><span class="sxs-lookup"><span data-stu-id="18f70-116">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

