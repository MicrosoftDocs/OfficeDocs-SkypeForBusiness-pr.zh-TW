---
title: Lync Server 2013 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f0aef4d3f2323bcfcd99f42b265ea02b6126b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="c21ef-102">Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c21ef-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c21ef-103">_**主題上次修改日期：** 2015年-04-08_</span><span class="sxs-lookup"><span data-stu-id="c21ef-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="c21ef-104">與 Enterprise Voice、 Lync Server 會傳遞至增強或取代傳統的專用交換機 (pbx) 系統提供獨立 Voice over Internet Protocol (VoIP)。</span><span class="sxs-lookup"><span data-stu-id="c21ef-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="c21ef-105">Enterprise Voice 使用者可以在您的組織在 VoIP 網路或 PBX 上呼叫同事，他們可以撥組織外部的傳統的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c21ef-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="c21ef-106">企業語音解決方案包含常見的通話功能，例如 answer、 轉寄、 轉接、 保留、 轉向、 發行及駐留，和增強型 9-1-1 (E9-1-1) 通話 （E9-1-1 是只適用於美國）。Enterprise Voice 也支援廣泛的目前和較舊的 IP 和 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="c21ef-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="c21ef-107">撥打和接聽電話</span><span class="sxs-lookup"><span data-stu-id="c21ef-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="c21ef-108">使用 Lync，使用者可以撥打電話，在其鍵盤上，輸入名稱或電話號碼，或使用其螢幕上顯示的撥號鍵台。</span><span class="sxs-lookup"><span data-stu-id="c21ef-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="c21ef-109">使用者也可以啟動直接從其連絡人清單的通話。</span><span class="sxs-lookup"><span data-stu-id="c21ef-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="c21ef-110">您也可以部署 Lync Phone Edition 裝置，也就是由 Microsoft 協力廠商所提供的獨立 IP 電話裝置。</span><span class="sxs-lookup"><span data-stu-id="c21ef-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="c21ef-111">使用者可以有多個登錄與 Lync Server 的電話裝置，且可以輕鬆地切換這些。</span><span class="sxs-lookup"><span data-stu-id="c21ef-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="c21ef-112">使用者會發出警示，其所有裝置上的傳入呼叫同時，IP 電話裝置上可自訂的鈴聲與類似於其電腦上的立即訊息通知。</span><span class="sxs-lookup"><span data-stu-id="c21ef-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="c21ef-113">使用者也可以設定連接至其電話機、 電腦和行動電話，讓他們可以達到不論它們的位置的單一電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c21ef-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="c21ef-114">基本通話功能</span><span class="sxs-lookup"><span data-stu-id="c21ef-114">Basic Call Features</span></span>

<span data-ttu-id="c21ef-115">在呼叫，使用者可以接聽其他來電或其中初始化的撥出電話，以及現有的作用中呼叫自動置於時保留。</span><span class="sxs-lookup"><span data-stu-id="c21ef-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="c21ef-116">到另一個，可以呼叫轉接從一位使用者，直接或之後的第一個使用者私下說出與第二個使用者。</span><span class="sxs-lookup"><span data-stu-id="c21ef-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="c21ef-117">使用者可以也將來電轉接給另一個裝置;例如，他們無法 active 來電轉接到行動電話為他們引導出其 office 門。</span><span class="sxs-lookup"><span data-stu-id="c21ef-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="c21ef-118">更豐富的通訊</span><span class="sxs-lookup"><span data-stu-id="c21ef-118">Richer Communications</span></span>

<span data-ttu-id="c21ef-119">當與另一位使用者使用 Lync 交談，使用者可以輕鬆地新增文字、 視訊或桌面共用的通話。</span><span class="sxs-lookup"><span data-stu-id="c21ef-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="c21ef-120">Do Not 打擾功能是與整合 Lync 中的目前狀態設定。</span><span class="sxs-lookup"><span data-stu-id="c21ef-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="c21ef-121">Exchange 整合通訊 (UM)、 Lync 與 Lync Server 整合與 Microsoft Exchange Server 2013 和 Microsoft Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="c21ef-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="c21ef-122">使用者可以查看是否有新語音郵件在其 Lync 視窗和電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="c21ef-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="c21ef-123">在 [電子郵件，他們可以按一下來播放語音信箱音訊中電子郵件訊息，或檢視語音信箱訊息的文稿 while。</span><span class="sxs-lookup"><span data-stu-id="c21ef-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="c21ef-124">進階通話功能</span><span class="sxs-lookup"><span data-stu-id="c21ef-124">Advanced Calling Features</span></span>

<span data-ttu-id="c21ef-125">Enterprise Voice 包含數項進階通話功能，例如 Lync 通話委派、 小組通話、 群組來電接聽和回應群組。</span><span class="sxs-lookup"><span data-stu-id="c21ef-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="c21ef-126">Lync 通話委派可讓使用者委派通話處理到一或多個助理員移至 [**工具** \> **選項** \> **呼叫轉寄設定**。</span><span class="sxs-lookup"><span data-stu-id="c21ef-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="c21ef-127">代理人可以多個呼叫代表執行工作的使用者，包括檢測通話、 進行呼叫，並啟動會議。</span><span class="sxs-lookup"><span data-stu-id="c21ef-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c21ef-128">您可能會尋找另一個類似命名功能，Lync 行事曆委派。</span><span class="sxs-lookup"><span data-stu-id="c21ef-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="c21ef-129">它不需要的企業語音功能，可讓使用者從 Outlook 的線上 Lync 會議排程。</span><span class="sxs-lookup"><span data-stu-id="c21ef-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="c21ef-130">如果您已在這裡尋找的資訊，建議您取出<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-csclientpolicy</A>上啟用 Exchange 委派同步處理的資訊。</span><span class="sxs-lookup"><span data-stu-id="c21ef-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="c21ef-131">小組通話可讓使用者使來電同時在組員的小組成員的電話，讓小組成員的任何人都可以接聽來電。</span><span class="sxs-lookup"><span data-stu-id="c21ef-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="c21ef-132">群組呼叫收取，Cumulative Updates for Lync Server 2013 中的新功能： 2 月 2013年可讓使用者接聽來電從他們自己的電話其同事。</span><span class="sxs-lookup"><span data-stu-id="c21ef-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="c21ef-133">群組來電接聽與小組通話中，主要的傳入呼叫只會在預定收件者的電話鈴響但任何其他使用者可以選擇接聽撥出通話收取群組號碼。</span><span class="sxs-lookup"><span data-stu-id="c21ef-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="c21ef-134">回應群組可以設定對指定的代理程式的佇列和聰明地路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="c21ef-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="c21ef-135">一般用途包括 IT 人員、 人力資源 hotlines 及其他內部的連絡人中心。</span><span class="sxs-lookup"><span data-stu-id="c21ef-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="c21ef-136">Enterprise Voice 管理</span><span class="sxs-lookup"><span data-stu-id="c21ef-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="c21ef-137">Lync Server 使用標準和發行的介面與現有基礎結構交互操作。</span><span class="sxs-lookup"><span data-stu-id="c21ef-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="c21ef-138">它支援閘道和 IP PBX 系統與 PSTN 網路，互相連線 （例如 SIP 主幹） SIP 選項，讓您可以將使用者移轉到 Enterprise Voice 一段時間，干擾降到最低。</span><span class="sxs-lookup"><span data-stu-id="c21ef-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="c21ef-139">Lync Server 與 VoIP 的傳統解決方案的互通性支援傳統 G.711、 G.722 等 G.723.1 轉碼器。</span><span class="sxs-lookup"><span data-stu-id="c21ef-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="c21ef-140">通話許可控制 (CAC)，與系統管理員可以設定 Lync Server 語音和視訊流量限制的網路連結上執行的數量的限制，並指定要將新的來電會超出限制要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="c21ef-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="c21ef-141">動作無法包含路由替代路徑，或拒絕來電。</span><span class="sxs-lookup"><span data-stu-id="c21ef-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="c21ef-142">Lync Server 的運作方式與協力廠商 Survivable Branch Appliance pstn 分公司，在中央網站的 WAN 故障時提供本地撥號服務和連線。</span><span class="sxs-lookup"><span data-stu-id="c21ef-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

