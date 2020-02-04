---
title: 配置 Lync Server 以搭配 System Center Operations Manager 使用
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
ms.openlocfilehash: f0cf422ddab501acf521c26c36d8f373bd42dbf9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="c4dbb-102">設定 Lync Server 2013 以搭配 System Center Operations Manager 使用</span><span class="sxs-lookup"><span data-stu-id="c4dbb-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4dbb-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c4dbb-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c4dbb-104">若要設定您的 Microsoft Lync Server 2013 基礎結構以搭配 System Center Operations Manager 使用，您必須執行下列三項操作：</span><span class="sxs-lookup"><span data-stu-id="c4dbb-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="c4dbb-105">找出並設定您的主要 System Center Operations Manager 管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="c4dbb-106">配置管理伺服器包括安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及使用 SQL Server 設定後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="c4dbb-107">您需要使用的實際 SQL Server 版本，取決於您所使用的 System Center 作業管理員版本。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="c4dbb-108">如需詳細資訊，請參閱[在 Lync server 2013 中設定主要管理伺服器](lync-server-2013-configuring-the-primary-management-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="c4dbb-109">找出並設定您想要監視的 Lync 伺服器電腦。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="c4dbb-110">若要使用 System Center Operations Manager 監視 Lync Server 電腦，您必須安裝 System Center Operations Manager 代理檔案，並將每個伺服器設定為充當 proxy。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="c4dbb-111">找出並設定您想要充當 Lync Server*觀察程式節點*的電腦。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="c4dbb-112">[觀察程式] 節點是定期執行 Lync Server 綜合交易的電腦，這些 Cmdlet 是確認重要 Lync 伺服器元件（例如登入系統或 exchange 立即訊息功能）的 Windows PowerShell Cmdlet。如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="c4dbb-113">本節中的主題包含執行這些任務的指示。</span><span class="sxs-lookup"><span data-stu-id="c4dbb-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c4dbb-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="c4dbb-114">In This Section</span></span>

  - [<span data-ttu-id="c4dbb-115">在 Lync Server 2013 中設定主要管理伺服器</span><span class="sxs-lookup"><span data-stu-id="c4dbb-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="c4dbb-116">安裝 Lync Server 2013 管理套件</span><span class="sxs-lookup"><span data-stu-id="c4dbb-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="c4dbb-117">設定將在 Lync Server 2013 中監視的 Lync Server 電腦</span><span class="sxs-lookup"><span data-stu-id="c4dbb-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="c4dbb-118">在 Lync Server 2013 中安裝及設定觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="c4dbb-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

