---
title: Lync Server 2013：設定撥入會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca8b82fe77e578f1ac513d00583c42dd56162a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="96122-102">在 Lync Server 2013 中設定撥入會議</span><span class="sxs-lookup"><span data-stu-id="96122-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96122-103">_**主題上次修改日期：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="96122-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="96122-104">本節將引導您完成 Lync Server 2013 電話撥入式會議的設定。</span><span class="sxs-lookup"><span data-stu-id="96122-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="96122-105">本節內容</span><span class="sxs-lookup"><span data-stu-id="96122-105">In This Section</span></span>

  - [<span data-ttu-id="96122-106">Lync Server 2013 中的電話撥入式會議組態先決條件和權限</span><span class="sxs-lookup"><span data-stu-id="96122-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="96122-107">Lync Server 2013 中的電話撥入式會議的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="96122-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="96122-108">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</span><span class="sxs-lookup"><span data-stu-id="96122-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="96122-109">確認 Lync Server 2013 已指派地區的撥號方案</span><span class="sxs-lookup"><span data-stu-id="96122-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="96122-110">(選用) 在 Lync Server 2013 中驗證 PIN 原則設定</span><span class="sxs-lookup"><span data-stu-id="96122-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="96122-111">在 Lync Server 2013 中設定電話撥入式會議的會議原則</span><span class="sxs-lookup"><span data-stu-id="96122-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="96122-112">在 Lync Server 2013 中設定電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="96122-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="96122-113">(選用) 在 Lync Server 2013 中驗證電話撥入式會議設定</span><span class="sxs-lookup"><span data-stu-id="96122-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="96122-114">(選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="96122-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="96122-115">(選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</span><span class="sxs-lookup"><span data-stu-id="96122-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="96122-116">Lync Server 2013 中的 (選用) 驗證電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="96122-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="96122-117">部署 Lync 2013 的線上會議增益集</span><span class="sxs-lookup"><span data-stu-id="96122-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="96122-118">在 Lync Server 2013 中設定使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="96122-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="96122-119">(建議) 建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="96122-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="96122-120">(選用) 在 Lync Server 2013 中歡迎使用者使用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="96122-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="96122-121">相關各節</span><span class="sxs-lookup"><span data-stu-id="96122-121">Related Sections</span></span>

[<span data-ttu-id="96122-122">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96122-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

