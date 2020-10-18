---
title: Lync Server 2013：宣告應用程式的簡介
description: Lync Server 2013：宣告應用程式的簡介。
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
ms.openlocfilehash: 15e9834be5edc67777f258f8d041e134287a891a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577249"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="6390e-103">Lync Server 2013 的宣告應用程式概述</span><span class="sxs-lookup"><span data-stu-id="6390e-103">Overview of the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6390e-104">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="6390e-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="6390e-105">當您部署宣告應用程式時，您必須設定未指派的號碼表，以決定當某人撥打未指派的號碼時要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="6390e-105">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="6390e-106">「未指派的號碼」表包含對組織有效的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。</span><span class="sxs-lookup"><span data-stu-id="6390e-106">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="6390e-107">當來電者撥打的電話號碼對您的組織而言是有效的，但是並未指派給任何人，Lync Server 會查詢未指派號碼路由表中的號碼，識別該號碼屬於哪一個範圍，並將通話路由傳送至該範圍所指定的宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="6390e-107">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="6390e-108">宣告應用程式會接聽來電，並 (如果將其設定為執行這項操作，則) 然後中斷通話，或將其轉接至預先決定的目的地，例如操作員。</span><span class="sxs-lookup"><span data-stu-id="6390e-108">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="6390e-109">您可以使用 Lync Server 管理命令介面 Cmdlet 來設定多個音訊訊息，或傳送目的地。</span><span class="sxs-lookup"><span data-stu-id="6390e-109">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="6390e-p102">設定未指派號碼表的方式取決於其使用方式。如果您有不再使用的特定號碼，而且想要播放專為各個號碼而設計的訊息，則可以在未指派號碼表中輸入那些特定號碼。例如，如果您變更了客戶服務中心的號碼，則可以輸入舊的客戶服務號碼，並將其與宣告相關聯，以提供新號碼。如果您想要對撥打未指派之號碼的任何人 (如離職員工) 播放一般訊息，則可以輸入您組織中所有有效分機的範圍。只要來電者撥打目前未指派的號碼，就會叫用未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="6390e-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="6390e-115">在 Lync Server 2013 中，宣告應用程式會自動隨回應群組應用程式一起安裝。</span><span class="sxs-lookup"><span data-stu-id="6390e-115">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="6390e-116">宣告及回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，會自動部署這兩個應用程式。</span><span class="sxs-lookup"><span data-stu-id="6390e-116">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

