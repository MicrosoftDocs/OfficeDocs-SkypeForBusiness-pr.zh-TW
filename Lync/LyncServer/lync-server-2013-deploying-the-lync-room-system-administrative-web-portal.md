---
title: Lync Server 2013：部署 Lync 會議室系統管理 Web 入口網站
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
ms.openlocfilehash: a7a7f3589f809fa9dfcbfa872653fb4cb8161ea8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522910"
---
# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="ef855-102">在 Lync Server 2013 中部署 Lync 會議室系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="ef855-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef855-103">_**主題上次修改日期：** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="ef855-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="ef855-104">Microsoft Lync Server 2013 Lync 會議室系統 (LRS) 系統管理 Web 入口網站是一個網頁入口網站，可供組織用來維護其 Lync 會議室系統會議室。</span><span class="sxs-lookup"><span data-stu-id="ef855-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="ef855-105">系統管理員可以使用 LRS 系統管理 Web 入口網站來監控 LRS 的健康情況，例如，監控連線的音訊/視頻裝置。</span><span class="sxs-lookup"><span data-stu-id="ef855-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="ef855-106">使用此入口網站，系統管理員可以遠端收集診斷資訊以監視會議室健康情況。</span><span class="sxs-lookup"><span data-stu-id="ef855-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="ef855-107">LRS 系統管理 Web 入口網站部署于每個 Lync 前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ef855-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="ef855-108">本指南為系統管理員提供如何安裝及設定 LRS 系統管理 Web 入口網站的指示。</span><span class="sxs-lookup"><span data-stu-id="ef855-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="ef855-109">其適用于具備 Lync Server 管理知識的系統管理員，以及具備修改 Lync Server 拓撲之系統管理員許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="ef855-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="ef855-110">在伺服器上部署 LRS 系統管理 Web 入口網站後，系統管理員可以從自己的電腦或膝上型電腦登入網站，以檢查所有 LRS 聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="ef855-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ef855-111">當您在 Microsoft Lync Server 2013 部署中安裝 LRS 系統管理 Web 入口網站時，您應該使用 <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync 會議室系統管理 Web 入口網站進行 Lync server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="ef855-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="ef855-112">LRS 系統管理 Web 入口網站的新版本可用於商務用 Skype Server 2015，但是除非您已部署商務用 Skype Server 2015，否則您不應該安裝該版本。</span><span class="sxs-lookup"><span data-stu-id="ef855-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="ef855-113">下載 <A href="https://go.microsoft.com/fwlink/?linkid=544807">適用于商務用 Skype Server 2015 的 Microsoft Lync 會議室系統管理 Web 入口網站</A>。</span><span class="sxs-lookup"><span data-stu-id="ef855-113">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef855-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ef855-114">In This Section</span></span>

[<span data-ttu-id="ef855-115">設定 lync 會議室系統管理 Web 入口網站的 Lync Server 2013 環境</span><span class="sxs-lookup"><span data-stu-id="ef855-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="ef855-116">在 Lync Server 2013 中安裝 Lync 會議室系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="ef855-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="ef855-117">在 Lync Server 2013 中使用 Lync 會議室系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="ef855-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef855-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ef855-118">See Also</span></span>


[<span data-ttu-id="ef855-119">在 Lync Server 2013 中部署會議</span><span class="sxs-lookup"><span data-stu-id="ef855-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

