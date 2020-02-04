---
title: Lync Server 2013：宣告應用程式簡介
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
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="bd12e-102">Lync Server 2013 中的宣告應用程式概覽</span><span class="sxs-lookup"><span data-stu-id="bd12e-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd12e-103">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="bd12e-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="bd12e-104">當您部署宣告應用程式時，您必須設定 [未指定的數位] 資料表，決定當有人撥打未指派的號碼時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="bd12e-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="bd12e-105">[未指定的數位] 表格包含適用于組織的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。</span><span class="sxs-lookup"><span data-stu-id="bd12e-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="bd12e-106">當來電者撥打電話給您的組織而言，但未指派給任何人時，Lync Server 會在未指定的數位路由表中查詢該號碼，找出該數位的範圍，並將呼叫路由到宣告為該範圍指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bd12e-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="bd12e-107">[宣告] 應用程式會應答通話並播放音訊訊息（如果您將它設定為這樣做），然後中斷通話，或將它轉移至預先確定的目的地，例如操作員。</span><span class="sxs-lookup"><span data-stu-id="bd12e-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="bd12e-108">您可以使用 Lync Server 管理命令介面 Cmdlet 來設定多個音訊訊息或傳輸目的地。</span><span class="sxs-lookup"><span data-stu-id="bd12e-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="bd12e-109">設定未指派號碼表的方式取決於其使用方式。</span><span class="sxs-lookup"><span data-stu-id="bd12e-109">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="bd12e-110">如果您的特定號碼已不再使用，而您想要播放專為每個數位提供的訊息，您可以在 [未指定的數位] 資料表中輸入那些特定的數位。</span><span class="sxs-lookup"><span data-stu-id="bd12e-110">If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table.</span></span> <span data-ttu-id="bd12e-111">例如，如果您變更了客戶服務服務台的號碼，您可以輸入舊的客戶服務號碼，並將其與提供新號碼的公告建立關聯。</span><span class="sxs-lookup"><span data-stu-id="bd12e-111">For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number.</span></span> <span data-ttu-id="bd12e-112">如果您想要在呼叫未獲指派之號碼的任何人（例如，針對離開貴組織的員工）發出一般訊息，您可以為組織中的所有有效延伸輸入範圍。</span><span class="sxs-lookup"><span data-stu-id="bd12e-112">If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization.</span></span> <span data-ttu-id="bd12e-113">每當來電者撥打目前未指派的號碼時，就會呼叫 [未指定的數位] 資料表。</span><span class="sxs-lookup"><span data-stu-id="bd12e-113">The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="bd12e-114">在 Lync Server 2013 中，宣告應用程式會自動與回應群組應用程式一起安裝。</span><span class="sxs-lookup"><span data-stu-id="bd12e-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="bd12e-115">宣告與回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，這兩個應用程式都會自動部署。</span><span class="sxs-lookup"><span data-stu-id="bd12e-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

