---
title: Lync Server 2013：設定新的受信任的應用程式伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="8b3a1-102">在 Lync Server 2013 中設定新的受信任應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="8b3a1-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b3a1-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8b3a1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8b3a1-104">受信任的應用程式是以 microsoft Lync Server 2013 信任的 Microsoft 整合通訊 Managed API （UCMA）3.0 核心 SDK 為基礎的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8b3a1-105">如需有關 UCMA 應用程式的詳細資訊，請參閱「統一通訊管理的[http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)API 3.0 核心 SDK 檔」。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="8b3a1-106">如需有關設定 Microsoft Outlook Web Access （OWA）和 Lync Server 2013 的詳細資訊，請參閱 Microsoft Exchange Server 2013 檔上的「設定 Outlook Web App 和 Lync Server 2010 整合」。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="8b3a1-107">若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="8b3a1-108">您也可以委派適當的管理員許可權與新增伺服器角色的許可權。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="8b3a1-109">如需詳細資訊，請參閱部署檔中的[Lync Server 2013 委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="8b3a1-110">針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="8b3a1-111">若要設定受信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="8b3a1-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="8b3a1-112">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="8b3a1-113">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="8b3a1-114">選取 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="8b3a1-115">在 [**另存拓朴為**] 對話方塊中，按一下您要使用的拓撲產生器檔案，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="8b3a1-116">在左窗格中，以滑鼠右鍵按一下 [**信任的應用程式伺服器**]，然後按一下 [**新增信任的應用程式池**]。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="8b3a1-117">輸入受信任的應用程式池的 [**池 FQDN** ]，選取它是否為單一伺服器或多重伺服器，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="8b3a1-118">在 [**選取下一個躍點]** 頁面上的清單中，選取 [Lync Server 2013 前端] 池。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="8b3a1-119">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="8b3a1-120">選取最上層節點的**Lync Server 2013**，然後從 [**動作**] 功能表中按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="8b3a1-121">**受信任的應用程式池**應該已成功建立，且與正確的 [前端] 池相關聯。</span><span class="sxs-lookup"><span data-stu-id="8b3a1-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

