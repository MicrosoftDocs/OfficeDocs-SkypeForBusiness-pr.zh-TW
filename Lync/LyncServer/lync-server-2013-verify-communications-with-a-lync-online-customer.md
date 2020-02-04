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
ms.openlocfilehash: f9b20be32ecbc7c3c684009c9c2f928c9dc897cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="f13d1-102">在 Lync Server 2013 中驗證與 Lync Online 客戶的通訊</span><span class="sxs-lookup"><span data-stu-id="f13d1-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f13d1-103">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="f13d1-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="f13d1-104">若要讓貴組織中的 Lync 使用者與 Microsoft Lync Online 2010 客戶的使用者進行通訊，您必須完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f13d1-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="f13d1-105">符合所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="f13d1-105">Met all prerequisites.</span></span> <span data-ttu-id="f13d1-106">這包括部署您的內部與邊緣伺服器、啟用貴組織的同盟支援，以及設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f13d1-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="f13d1-107">如需詳細資訊，請參閱[在 Lync Server 2013 中與 Lync Online 客戶進行聯盟的先決條件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)。</span><span class="sxs-lookup"><span data-stu-id="f13d1-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="f13d1-108">在內部部署中設定網域存取支援。</span><span class="sxs-lookup"><span data-stu-id="f13d1-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="f13d1-109">這包括建立主機提供者專案並將您的部署設定為允許從 Lync Online 客戶的網域存取。</span><span class="sxs-lookup"><span data-stu-id="f13d1-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="f13d1-110">如需詳細資訊，請參閱[在 Lync Server 2013 中設定 Lync Online 網域的同盟支援](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="f13d1-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="f13d1-111">已將您的使用者帳戶設定為支援同盟。</span><span class="sxs-lookup"><span data-stu-id="f13d1-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="f13d1-112">如需詳細資訊，請參閱[在 Lync Server 2013 中設定與 Lync Online 客戶的同盟的使用者存取權](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)。</span><span class="sxs-lookup"><span data-stu-id="f13d1-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="f13d1-113">完成所有這些步驟之後，Lync Online 2010 客戶的所有設定都完成了其線上服務的所有設定，以支援與貴組織的同盟，請透過測試內部網路間的通訊來驗證通訊貴組織中的使用者，以及 Lync Online 客戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="f13d1-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="f13d1-114">如果通訊失敗，請使用邊緣伺服器的記錄工具來捕獲記錄和追蹤檔案，以便對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="f13d1-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="f13d1-115">如需使用記錄工具的詳細資料，請參閱在作業檔中[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f13d1-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="f13d1-116">如需記錄工具的詳細資訊，請參閱 TechNet Library 上的 Lync Server 2010 記錄工具檔[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)。</span><span class="sxs-lookup"><span data-stu-id="f13d1-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

