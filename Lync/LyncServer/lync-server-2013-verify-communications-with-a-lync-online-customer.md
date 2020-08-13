---
title: Lync Server 2013：驗證與 Lync Online 客戶的通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03aae75cfdb3e179347d14c6f42a90ffe060fad7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="0d16d-102">在 Lync Server 2013 中驗證與 Lync Online 客戶的通訊</span><span class="sxs-lookup"><span data-stu-id="0d16d-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d16d-103">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="0d16d-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="0d16d-104">若要讓組織中的 Lync 使用者能夠與 Microsoft Lync Online 2010 客戶的使用者進行通訊，您必須完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0d16d-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="0d16d-105">符合所有必要條件。</span><span class="sxs-lookup"><span data-stu-id="0d16d-105">Met all prerequisites.</span></span> <span data-ttu-id="0d16d-106">這包括部署您的內部及 edge 伺服器、啟用組織的同盟支援和設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0d16d-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="0d16d-107">如需詳細資訊，請參閱 [在 Lync Server 2013 中與 Lync Online 客戶進行同盟的必要條件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)。</span><span class="sxs-lookup"><span data-stu-id="0d16d-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="0d16d-108">設定內部部署中的網域存取支援。</span><span class="sxs-lookup"><span data-stu-id="0d16d-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="0d16d-109">這包括建立主機提供者專案及設定您的部署，以允許從 Lync Online 客戶的網域存取。</span><span class="sxs-lookup"><span data-stu-id="0d16d-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="0d16d-110">如需詳細資訊，請參閱 [Configure federation support for a Lync Online domain In Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="0d16d-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="0d16d-111">設定您的使用者帳戶以支援同盟。</span><span class="sxs-lookup"><span data-stu-id="0d16d-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="0d16d-112">如需詳細資訊，請參閱 [Configure user access for 同盟 with a Lync Online 客戶 In Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)。</span><span class="sxs-lookup"><span data-stu-id="0d16d-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="0d16d-113">完成所有這些步驟之後，如果 Lync Online 2010 客戶的所有設定都完成其線上服務的所有設定，以支援與組織的同盟，請測試組織內部使用者與 Lync Online 客戶的使用者之間的通訊，以驗證通訊。</span><span class="sxs-lookup"><span data-stu-id="0d16d-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="0d16d-114">如果通訊不成功，請使用 Edge Server 中的記錄工具來捕獲記錄檔和追蹤檔，以便疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="0d16d-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="0d16d-115">如需使用記錄工具的詳細資訊，請參閱 Operations 檔中的 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md) 。</span><span class="sxs-lookup"><span data-stu-id="0d16d-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="0d16d-116">如需有關記錄工具的詳細資訊，請參閱 TechNet 文件庫上的 Lync Server 2010 記錄工具檔 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) 。</span><span class="sxs-lookup"><span data-stu-id="0d16d-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

