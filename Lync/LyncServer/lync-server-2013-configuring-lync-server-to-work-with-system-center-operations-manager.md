---
title: 設定 Lync Server 以搭配 System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88eeae2c08020aacb142bbceb6c2637ae4d55b63
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="86e2f-102">設定 Lync Server 2013 來使用 System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="86e2f-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86e2f-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="86e2f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="86e2f-104">若要設定您的 Microsoft Lync Server 2013 基礎結構，以搭配 System Center Operations Manager 中，您必須執行下列三個動作：</span><span class="sxs-lookup"><span data-stu-id="86e2f-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="86e2f-105">找出並將您主要的 System Center Operations Manager 管理伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="86e2f-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="86e2f-106">設定管理伺服器包括安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及設定使用 SQL Server 後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="86e2f-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="86e2f-107">您必須使用 SQL Server 的實際版本取決於您使用 System Center Operations Manager 的版本。</span><span class="sxs-lookup"><span data-stu-id="86e2f-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="86e2f-108">如需詳細資訊，請參閱[設定 Lync Server 2013 中的主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)。</span><span class="sxs-lookup"><span data-stu-id="86e2f-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="86e2f-109">找出並設定您想要監視的 Lync Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="86e2f-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="86e2f-110">若要使用 System Center Operations Manager 監視 Lync Server 的電腦中，您必須安裝 System Center Operations Manager 代理程式檔案，並設定每一部要作為 proxy。</span><span class="sxs-lookup"><span data-stu-id="86e2f-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="86e2f-111">找出並設定您想要做為 Lync Server*監看員節點*的電腦。</span><span class="sxs-lookup"><span data-stu-id="86e2f-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="86e2f-112">監看員節點會定期執行 Lync Server 綜合交易，也就是確認重要的 Lync Server 元件，例如能夠登入系統或交換立即訊息的能力的 Windows PowerShell cmdlet 的電腦如預期運作。</span><span class="sxs-lookup"><span data-stu-id="86e2f-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="86e2f-113">本節中的主題包含執行每項工作的指示。</span><span class="sxs-lookup"><span data-stu-id="86e2f-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="86e2f-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="86e2f-114">In This Section</span></span>

  - [<span data-ttu-id="86e2f-115">在 Lync Server 2013 中設定的主要管理伺服器</span><span class="sxs-lookup"><span data-stu-id="86e2f-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="86e2f-116">安裝 Lync Server 2013 管理組件</span><span class="sxs-lookup"><span data-stu-id="86e2f-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="86e2f-117">在 Lync Server 2013 中設定要監控的 Lync Server 電腦</span><span class="sxs-lookup"><span data-stu-id="86e2f-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="86e2f-118">安裝和設定 Lync Server 2013 中的監看員節點</span><span class="sxs-lookup"><span data-stu-id="86e2f-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

