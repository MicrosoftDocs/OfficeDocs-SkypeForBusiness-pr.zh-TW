---
title: 宣告應用程式的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264fbf5faf3fbce830a8d55cd7626d1ff67c2d58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="ee364-102">Lync Server 2013 中的宣告應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="ee364-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee364-103">_**主題上次修改日期：** 2012年-09-13_</span><span class="sxs-lookup"><span data-stu-id="ee364-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="ee364-104">當您部署宣告應用程式時，您需要設定會決定當有人撥打未指派的號碼時應採取的動作未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="ee364-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="ee364-105">未指派號碼表格包含的有效值為組織的電話號碼範圍，並指定哪些宣告應用程式會處理每個範圍。</span><span class="sxs-lookup"><span data-stu-id="ee364-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="ee364-106">當來電者撥打組織有效，但不指派給任何人的電話號碼時，Lync Server 會查閱未指派號碼的路由表格中的數字、 識別哪一個範圍中，就是數字落和宣告將通話路由傳送指定為該範圍的應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee364-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="ee364-107">宣告應用程式接聽來電播放的語音訊息 （如果您設定要這麼做），然後中斷來電或將其移至預定目的地，例如運算子。</span><span class="sxs-lookup"><span data-stu-id="ee364-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="ee364-108">您可以使用 Lync Server 管理命令介面指令程式，來設定多個音訊的郵件，或傳輸的目的地。</span><span class="sxs-lookup"><span data-stu-id="ee364-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="ee364-p102">設定未指派號碼表的方式取決於其使用方式。如果您有不再使用的特定號碼，而且想要播放專為各個號碼而設計的訊息，則可以在未指派號碼表中輸入那些特定號碼。例如，如果您變更了客戶服務中心的號碼，則可以輸入舊的客戶服務號碼，並將其與宣告相關聯，以提供新號碼。如果您想要對撥打未指派之號碼的任何人 (如離職員工) 播放一般訊息，則可以輸入您組織中所有有效分機的範圍。只要來電者撥打目前未指派的號碼，就會叫用未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="ee364-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="ee364-114">在 Lync Server 2013 中，宣告應用程式會自動安裝與回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee364-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="ee364-115">宣告和回應群組應用程式是標準的企業語音部署的元件： 當您部署企業語音時，這些應用程式均會自動部署。</span><span class="sxs-lookup"><span data-stu-id="ee364-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

