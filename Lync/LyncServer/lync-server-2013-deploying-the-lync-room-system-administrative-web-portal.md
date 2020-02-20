---
title: Lync Server 2013： 部署 Lync 會議室系統管理的入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0c352e9e890611d95a7d562a88ae8f6cebc7243
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="7b93f-102">部署 Lync Server 2013 中的管理 Web Lync 會議室系統入口網站</span><span class="sxs-lookup"><span data-stu-id="7b93f-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b93f-103">_**主題上次修改日期：** 2015年-05-04_</span><span class="sxs-lookup"><span data-stu-id="7b93f-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="7b93f-104">Microsoft Lync Server 2013 Lync 會議室系統 (LRS) 系統管理入口網站是入口網站，讓組織可用於維護其 Lync 會議室系統會議室。</span><span class="sxs-lookup"><span data-stu-id="7b93f-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="7b93f-105">管理員可以使用 LRS 管理入口網站來監控 LRS 健康情況，例如藉由監視音訊/視訊裝置的連線。</span><span class="sxs-lookup"><span data-stu-id="7b93f-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="7b93f-106">使用此入口網站，系統管理員可以從遠端收集診斷資訊給監視會議會議室健康情況。</span><span class="sxs-lookup"><span data-stu-id="7b93f-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="7b93f-107">LRS 管理入口網站被部署在每個 Lync 前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="7b93f-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="7b93f-108">本指南提供有關如何安裝及設定 LRS 管理入口網站管理員的指示。</span><span class="sxs-lookup"><span data-stu-id="7b93f-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="7b93f-109">它適用於系統管理員擁有知曉 Lync Server 管理，以及誰具有系統管理員使用者權限，可修改 Lync Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b93f-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="7b93f-110">LRS 管理入口網站部署在伺服器上後，系統管理員可以從他們自己的筆記型電腦或電腦登入的網站，查看所有 LRS 會議室的狀態。</span><span class="sxs-lookup"><span data-stu-id="7b93f-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7b93f-111">當您在 Microsoft Lync Server 2013 部署中安裝 LRS 管理入口網站時，您應該使用<A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync 會議室系統管理入口網站的 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="7b93f-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="7b93f-112">LRS 管理入口網站的新版本適用於商務用 Skype Server 2015，但是您不應該安裝該版本，除非您已部署用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="7b93f-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="7b93f-113">下載<A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync 會議室系統管理 Web Skype for Business Server 2015 入口網站</A>。</span><span class="sxs-lookup"><span data-stu-id="7b93f-113">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b93f-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7b93f-114">In This Section</span></span>

[<span data-ttu-id="7b93f-115">設定 Lync Server 2013 環境的 Lync 會議室系統管理入口網站</span><span class="sxs-lookup"><span data-stu-id="7b93f-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="7b93f-116">安裝 Lync Server 2013 中的 Lync 會議室系統管理的入口網站</span><span class="sxs-lookup"><span data-stu-id="7b93f-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="7b93f-117">使用 Lync Server 2013 中的 Lync 會議室系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="7b93f-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7b93f-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b93f-118">See Also</span></span>


[<span data-ttu-id="7b93f-119">部署 Lync Server 2013 中的會議</span><span class="sxs-lookup"><span data-stu-id="7b93f-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

