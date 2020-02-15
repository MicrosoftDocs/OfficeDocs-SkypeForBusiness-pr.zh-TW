---
title: 使用 Exchange Server 整合時，設定原則的封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac425f08e3522c4ed885036c144c4c0f12e37b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="f5459-102">使用 Exchange Server 整合時，Lync Server 2013 中的封存原則設定</span><span class="sxs-lookup"><span data-stu-id="f5459-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5459-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="f5459-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f5459-104">如果隸屬於 Exchange 2013 使用者可以放入原有範圍暫止，這些使用者的封存 Exchange 就地保留原則控制其信箱。</span><span class="sxs-lookup"><span data-stu-id="f5459-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="f5459-105">如果您使用 Microsoft Exchange 整合您的部署時，Exchange 2013 原則會覆寫 Lync Server 封存原則位於 Exchange 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5459-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="f5459-106">如需設定 Exchange 封存原則的詳細資訊，請參閱 < Exchange 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="f5459-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="f5459-107">如需詳細資訊設定使用者原則的使用者及位於 Lync Server 2013，請參閱部署文件中的[Lync Server 2013 中的封存使用者原則設定](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f5459-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="f5459-108">如需原則的運作方式的詳細資訊，請參閱規劃文件、 部署文件或作業文件中的[如何封存的 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="f5459-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f5459-109">如果您部署 Exchange 2013 和 Lync Server 2013 相同樹系中，在您 Exchange 2013 的就地保留原則控制封存。</span><span class="sxs-lookup"><span data-stu-id="f5459-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="f5459-110">如果您部署 Exchange 2013 和 Lync Server 2013，在不同樹系，請參閱 「 部署 Lync Server 和 Microsoft Exchange 中不同樹系 「 <A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的封存的部署檢查清單</A>中。</span><span class="sxs-lookup"><span data-stu-id="f5459-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

