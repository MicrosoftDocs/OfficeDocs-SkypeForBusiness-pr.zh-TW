---
title: Lync Server 2013：設定電話撥入式會議
description: Lync Server 2013：設定電話撥入式會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9c3353caa1344b717b0f64c271149f078f194e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557939"
---
# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="95887-103">在 Lync Server 2013 中設定電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="95887-103">Configuring dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95887-104">_**主題上次修改日期：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="95887-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="95887-105">本節會引導您完成 Lync Server 2013 電話撥入式會議的設定。</span><span class="sxs-lookup"><span data-stu-id="95887-105">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="95887-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="95887-106">In This Section</span></span>

  - [<span data-ttu-id="95887-107">Lync Server 2013 中的電話撥入式會議設定必要條件和許可權</span><span class="sxs-lookup"><span data-stu-id="95887-107">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="95887-108">Lync Server 2013 中的電話撥入式會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="95887-108">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="95887-109">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</span><span class="sxs-lookup"><span data-stu-id="95887-109">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="95887-110">確定撥號對應表 Lync Server 2013 具有指派的區域</span><span class="sxs-lookup"><span data-stu-id="95887-110">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="95887-111"> (選用) 驗證 Lync Server 2013 中的 PIN 原則設定</span><span class="sxs-lookup"><span data-stu-id="95887-111">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="95887-112">在 Lync Server 2013 中設定電話撥入式會議原則</span><span class="sxs-lookup"><span data-stu-id="95887-112">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="95887-113">在 Lync Server 2013 中設定電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="95887-113">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="95887-114"> (選用) 驗證 Lync Server 2013 中的電話撥入式會議設定</span><span class="sxs-lookup"><span data-stu-id="95887-114">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="95887-115"> (選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="95887-115">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="95887-116"> (選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</span><span class="sxs-lookup"><span data-stu-id="95887-116">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="95887-117"> (選用) 驗證 Lync Server 2013 中的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="95887-117">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="95887-118">部署 Lync 2013 的線上會議增益集</span><span class="sxs-lookup"><span data-stu-id="95887-118">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="95887-119">在 Lync Server 2013 中設定使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="95887-119">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="95887-120"> (建議) 建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="95887-120">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="95887-121"> 在 Lync Server 2013 中 (選用) 歡迎使用者撥入式會議</span><span class="sxs-lookup"><span data-stu-id="95887-121">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="95887-122">相關各節</span><span class="sxs-lookup"><span data-stu-id="95887-122">Related Sections</span></span>

[<span data-ttu-id="95887-123">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95887-123">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

