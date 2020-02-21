---
title: 'Lync Server 2013: Enterprise Voice 的軟體先決條件'
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
ms.openlocfilehash: 9a4b0b2e2708abbf3b92223474ec0804c1d11ac8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="78d90-102">Lync Server 2013 中的 Enterprise Voice 的軟體先決條件</span><span class="sxs-lookup"><span data-stu-id="78d90-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78d90-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="78d90-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="78d90-104">確認您想要部署 Enterprise Voice 的基礎結構符合下列軟體先決條件：</span><span class="sxs-lookup"><span data-stu-id="78d90-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="78d90-105">Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且正在運作您網路上。</span><span class="sxs-lookup"><span data-stu-id="78d90-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="78d90-106">所有 Edge Server 都都已部署、 作業在周邊網路，包括 Edge 伺服器執行 Access Edge service 為 A / V Edge service、 Web Conferencing Edge service 和反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="78d90-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="78d90-107">Microsoft Exchange Server 2007 Service Pack 3 (SP3)、 Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013 才整合 Exchange 整合通訊與 Lync Server，以及用於提供豐富的通知及通話記錄資訊Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="78d90-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="78d90-108">已建立並啟用 Lync Server 的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="78d90-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="78d90-109">Lync 用戶端和裝置已成功部署。</span><span class="sxs-lookup"><span data-stu-id="78d90-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="78d90-110">在您網路上的伺服器上安裝拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="78d90-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="78d90-111">後續步驟：確認安全性和設定先決條件</span><span class="sxs-lookup"><span data-stu-id="78d90-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="78d90-112">確認 Enterprise Voice 的軟體先決條件後，您可以參考文件說明，繼續準備部署 Enterprise Voice：</span><span class="sxs-lookup"><span data-stu-id="78d90-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="78d90-113">確認安全性、 使用者設定和硬體 environmental [Lync Server 2013 中的 Enterprise voice 的安全性和組態必要條件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="78d90-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="78d90-114">安裝中繼伺服器中所述[安裝中繼伺服器在 Lync Server 2013 中的檔案](lync-server-2013-install-the-files-for-mediation-server.md)，但*僅限*如果您想要部署獨立中繼伺服器或集區，因為中繼伺服器安裝為前端集區或 Standard Edition server 部署程序時組合的一部分。</span><span class="sxs-lookup"><span data-stu-id="78d90-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="78d90-115">設定主幹連線以提供 PSTN 連線的使用者，[在 Lync Server 2013 中的 Configuring trunks](lync-server-2013-configuring-trunks.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="78d90-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

