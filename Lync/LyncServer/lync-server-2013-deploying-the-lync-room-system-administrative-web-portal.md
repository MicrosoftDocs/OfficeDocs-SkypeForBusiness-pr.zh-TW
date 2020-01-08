---
title: Lync Server 2013：部署 Lync 會議室系統管理網頁入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fc5e7d0f136481ddce5d34de41268cb224822e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="4c73f-102">在 Lync Server 2013 中部署 Lync 會議室系統管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="4c73f-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c73f-103">_**主題上次修改日期：** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="4c73f-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="4c73f-104">Microsoft Lync Server 2013 Lync 室系統（LRS）的系統管理網頁入口網站是一個組織可以用來維護其 Lync 會議室系統會議室的網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="4c73f-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="4c73f-105">系統管理員可以使用 LRS 的系統管理網頁入口網站來監視 LRS 的健康情況，例如，監視連線的音訊/視頻裝置。</span><span class="sxs-lookup"><span data-stu-id="4c73f-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="4c73f-106">有了這個入口網站，管理員就可以遠端收集診斷資訊來監控會議室的健康情況。</span><span class="sxs-lookup"><span data-stu-id="4c73f-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="4c73f-107">LRS 系統管理網頁入口網站已部署在每個 Lync 前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4c73f-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="4c73f-108">本指南提供系統管理員如何安裝及設定 LRS 系統管理網頁入口網站的相關指示。</span><span class="sxs-lookup"><span data-stu-id="4c73f-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="4c73f-109">它適用于熟悉 Lync Server 管理的系統管理員，以及誰有管理員使用者許可權來修改 Lync Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="4c73f-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="4c73f-110">在伺服器上部署 LRS 系統管理網路入口網站之後，系統管理員可以從自己的電腦或膝上型電腦登入網站，以檢查所有 LRS 聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="4c73f-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4c73f-111">當您在 Microsoft Lync Server 2013 部署中安裝 LRS 系統管理網頁入口網站時，請使用<A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync 會議室系統的系統管理網頁入口網站進行 Lync server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="4c73f-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="4c73f-112">商務用 Skype Server 2015 有新版本的 LRS 系統管理網頁入口網站，但除非您已部署商務用 Skype Server 2015，否則您不應該安裝該版本。</span><span class="sxs-lookup"><span data-stu-id="4c73f-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="4c73f-113">下載<A href="http://go.microsoft.com/fwlink/?linkid=544807">適用于商務用 Skype Server 2015 的 Microsoft Lync 會議室系統管理網頁入口網站</A>。</span><span class="sxs-lookup"><span data-stu-id="4c73f-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4c73f-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="4c73f-114">In This Section</span></span>

[<span data-ttu-id="4c73f-115">為 Lync Room System Administrative Web Portal 設定您的 Lync Server 2013 環境</span><span class="sxs-lookup"><span data-stu-id="4c73f-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="4c73f-116">在 Lync Server 2013 中安裝 Lync 會議室系統管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="4c73f-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="4c73f-117">在 Lync Server 2013 中使用 Lync Room System 系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="4c73f-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c73f-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="4c73f-118">See Also</span></span>


[<span data-ttu-id="4c73f-119">在 Lync Server 2013 中部署會議</span><span class="sxs-lookup"><span data-stu-id="4c73f-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

