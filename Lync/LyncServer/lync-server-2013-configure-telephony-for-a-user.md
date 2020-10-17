---
title: Lync Server 2013：設定使用者的電話語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86eade8f7a2ac1db627668ca78b8fb7869e6da71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520370"
---
# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="919ad-102">在 Lync Server 2013 中設定使用者的電話語音</span><span class="sxs-lookup"><span data-stu-id="919ad-102">Configure telephony for a user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="919ad-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="919ad-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="919ad-104">電話語音設定是使用者帳戶的一些個別設定，可在 Lync Server 控制台中針對使用者 (設定，也就是說，如果個別使用者已啟用 Lync Server 2013，而組織支援電話語音) 。</span><span class="sxs-lookup"><span data-stu-id="919ad-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="919ad-105">Lync Server 使用者電話語音選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="919ad-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="919ad-106">**已停用**     音訊/視頻使用者無法使用音訊和影片進行通話。</span><span class="sxs-lookup"><span data-stu-id="919ad-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="919ad-107">**僅限**     電腦對電腦使用者只能進行電腦對電腦音訊或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="919ad-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="919ad-108">**Enterprise Voice**    使用者可以使用 Lync Server 2013 基礎結構路由傳送所有來電和撥出電話。</span><span class="sxs-lookup"><span data-stu-id="919ad-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="919ad-109">使用者也可以進行電腦對電腦呼叫。</span><span class="sxs-lookup"><span data-stu-id="919ad-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="919ad-110">**遠端呼叫控制**    使用者可以使用 Lync Server 2013 來控制電腦電話，也可以進行電腦對電腦通話。</span><span class="sxs-lookup"><span data-stu-id="919ad-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="919ad-111">如需設定組織之電話語音的詳細資訊，請參閱部署檔中的在 lync Server [2013 中設定使用者的電話語音](lync-server-2013-configure-telephony-for-a-user.md) ，以及在 [lync Server 2013 中部署 Enterprise Voice](lync-server-2013-deploying-enterprise-voice.md) 。</span><span class="sxs-lookup"><span data-stu-id="919ad-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="919ad-112">若要設定特定使用者帳戶的電話語音</span><span class="sxs-lookup"><span data-stu-id="919ad-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="919ad-113">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="919ad-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="919ad-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="919ad-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="919ad-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="919ad-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="919ad-116">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="919ad-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="919ad-117">在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="919ad-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="919ad-118">在表格中，按一下您要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="919ad-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="919ad-119">在 **[編輯]** 功能表中，按一下 **[修改]**。</span><span class="sxs-lookup"><span data-stu-id="919ad-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="919ad-120">在 **[電話語音]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="919ad-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="919ad-121">若要停用使用者的音訊和視訊電話，請按一下 **[音訊/視訊已停用]**。</span><span class="sxs-lookup"><span data-stu-id="919ad-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="919ad-p103">若要啟用使用者的電腦對電腦音訊通訊，但不啟用遠端呼叫控制或 Enterprise Voice，請按一下 **[僅限電腦對電腦]**。針對使用者用於電腦對電腦音訊通訊的電話，指定 **[線路 URI]** 值。</span><span class="sxs-lookup"><span data-stu-id="919ad-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="919ad-124">若要依照服務原則類別（包括 PC 對電腦音訊通訊）使用 Lync Server 2010 基礎結構來路由傳送使用者的電話，請按一下 [ **Enterprise Voice**]。</span><span class="sxs-lookup"><span data-stu-id="919ad-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="919ad-125">在 **[線路 URI]** 中，指定 Enterprise Voice 的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="919ad-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="919ad-126">在 **[撥號對應表原則]** 和 **[語音原則]** 中，指定使用者的適當原則。</span><span class="sxs-lookup"><span data-stu-id="919ad-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="919ad-127">若要指定將使用者撥打的電話號碼轉譯為 E.164 格式時的正規化規則，請在 **[位置原則]** 中選取適當的位置設定檔。</span><span class="sxs-lookup"><span data-stu-id="919ad-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="919ad-128">若要啟用遠端呼叫控制，可讓使用者從 Lync Server 2013 控制其桌面電話線路，以進行 PC 對電腦通話和 PC 對電話的呼叫，請按一下 [ **遠端呼叫控制**]。</span><span class="sxs-lookup"><span data-stu-id="919ad-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="919ad-129">在 **[線路 URI]** 中，指定遠端呼叫控制的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="919ad-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="919ad-130">使用者必須有桌上電話和用於電話路由的專用交換機 (PBX) 連線。</span><span class="sxs-lookup"><span data-stu-id="919ad-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="919ad-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="919ad-131">See Also</span></span>


[<span data-ttu-id="919ad-132">在 Lync Server 2013 中修改使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="919ad-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

