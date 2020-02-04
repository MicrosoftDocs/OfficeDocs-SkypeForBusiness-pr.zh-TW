---
title: 防止服務的工作階段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8fb96fef5a01f9b25ca954dd27d1bdfd1f7055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="f8e81-102">防止服務的工作階段</span><span class="sxs-lookup"><span data-stu-id="f8e81-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8e81-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f8e81-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f8e81-104">您可以使用 Microsoft Lync Server 2010 [控制台] 來避免在特定電腦上執行的所有 Lync Server 2010 服務的新會話，或避免特定 Lync Server 2010 服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="f8e81-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="f8e81-105">避免電腦上所有 Lync Server 服務的新會話</span><span class="sxs-lookup"><span data-stu-id="f8e81-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="f8e81-106">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f8e81-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f8e81-107">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f8e81-108">在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="f8e81-109">在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您想要防止新會話之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="f8e81-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="f8e81-110">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-110">Click **Action**.</span></span>

6.  <span data-ttu-id="f8e81-111">按一下 [**防止所有服務的新會話**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="f8e81-112">若要防止特定服務的新會話</span><span class="sxs-lookup"><span data-stu-id="f8e81-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="f8e81-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f8e81-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f8e81-114">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f8e81-115">在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="f8e81-116">在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。</span><span class="sxs-lookup"><span data-stu-id="f8e81-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="f8e81-117">按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="f8e81-118">如有需要，請排序服務清單，然後按一下您要防止新會話的服務。</span><span class="sxs-lookup"><span data-stu-id="f8e81-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="f8e81-119">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-119">Click **Action**.</span></span>

8.  <span data-ttu-id="f8e81-120">按一下 [**避免新的服務會話**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="f8e81-121">按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f8e81-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

