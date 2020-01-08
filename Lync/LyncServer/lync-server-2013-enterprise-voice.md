---
title: Lync Server 2013 企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="183a6-102">Lync Server 2013 中的企業語音</span><span class="sxs-lookup"><span data-stu-id="183a6-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="183a6-103">_**主題上次修改日期：** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="183a6-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="183a6-104">透過企業語音，Lync Server 會提供獨立的網際網路通訊協定（VoIP）產品，以增強或取代傳統的專用分支 exchange （PBX）系統。</span><span class="sxs-lookup"><span data-stu-id="183a6-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="183a6-105">企業語音使用者可以呼叫貴組織的 VoIP 網路或 PBX 上的同事，而且可以呼叫貴組織外部的傳統電話號碼。</span><span class="sxs-lookup"><span data-stu-id="183a6-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="183a6-106">企業語音方案包含常見的呼叫功能，例如 [應答]、[轉寄]、[轉接]、[保留]、[轉移]、[發行及寄存]，以及 [增強9-1-1 （E9-1）] 呼叫（僅適用于美國的 E9-1-1）。企業語音也支援各種目前及較舊的 IP 和 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="183a6-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="183a6-107">撥打電話和接聽通話</span><span class="sxs-lookup"><span data-stu-id="183a6-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="183a6-108">使用者可以使用 Lync 在鍵盤上輸入名稱或電話號碼，或使用螢幕上顯示的撥號鍵台來撥打通話。</span><span class="sxs-lookup"><span data-stu-id="183a6-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="183a6-109">使用者也可以直接從連絡人清單中啟動通話。</span><span class="sxs-lookup"><span data-stu-id="183a6-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="183a6-110">您也可以部署 Lync Phone Edition 裝置，這些裝置是由 Microsoft 合作夥伴提供的獨立 IP 電話裝置。</span><span class="sxs-lookup"><span data-stu-id="183a6-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="183a6-111">使用者可以有多個註冊到 Lync Server 的電話裝置，而且可以輕鬆地在這些裝置之間切換。</span><span class="sxs-lookup"><span data-stu-id="183a6-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="183a6-112">使用者會在其所有裝置上同時收到來電通知，且在 IP 電話裝置上有可自訂的鈴聲，以及電腦上的立即訊息等類似通知。</span><span class="sxs-lookup"><span data-stu-id="183a6-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="183a6-113">使用者也可以設定連線到其手機、電腦和手機的單一電話號碼，讓他們無論身在何處都能到達。</span><span class="sxs-lookup"><span data-stu-id="183a6-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="183a6-114">基本通話功能</span><span class="sxs-lookup"><span data-stu-id="183a6-114">Basic Call Features</span></span>

<span data-ttu-id="183a6-115">在通話時，使用者可以接聽其他來電或發起撥出電話，而現有的使用中通話則會自動停留在保留狀態。</span><span class="sxs-lookup"><span data-stu-id="183a6-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="183a6-116">您可以直接或在第一位使用者使用第二個使用者進行私下演講之後，將通話從一個使用者轉接到另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="183a6-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="183a6-117">使用者也可以將來電轉接到另一個裝置;例如，他們可以將使用中的來電轉接到他們的行動電話，因為他們會離開其辦公室的大門。</span><span class="sxs-lookup"><span data-stu-id="183a6-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="183a6-118">更豐富的通訊</span><span class="sxs-lookup"><span data-stu-id="183a6-118">Richer Communications</span></span>

<span data-ttu-id="183a6-119">當您使用 Lync 與其他使用者交談時，使用者可以輕鬆地在通話中新增文字、影片或桌面共用。</span><span class="sxs-lookup"><span data-stu-id="183a6-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="183a6-120">[請勿打擾] 功能已與 Lync 中的目前狀態設定整合。</span><span class="sxs-lookup"><span data-stu-id="183a6-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="183a6-121">使用 Exchange 整合通訊（UM），Lync 和 Lync Server 整合至 Microsoft Exchange Server 2013 與 Microsoft Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="183a6-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="183a6-122">使用者可以查看他們在 Lync 視窗和電子郵件中是否有新的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="183a6-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="183a6-123">在電子郵件中，他們可以按一下以在電子郵件訊息中播放語音信箱音訊，或查看語音信箱訊息的記錄。</span><span class="sxs-lookup"><span data-stu-id="183a6-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="183a6-124">高級通話功能</span><span class="sxs-lookup"><span data-stu-id="183a6-124">Advanced Calling Features</span></span>

<span data-ttu-id="183a6-125">企業語音還包含數種高級通話功能，例如 Lync 通話委派、小組通話、群組通話挑選，以及回應群組。</span><span class="sxs-lookup"><span data-stu-id="183a6-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="183a6-126">Lync 通話委派可讓使用者將呼叫處理委派給一或多個助手，方法是移至 [**工具** \> **] 選項** \>的 [**來電轉接設定**]。</span><span class="sxs-lookup"><span data-stu-id="183a6-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="183a6-127">代理人可以代表使用者執行多個通話工作，包括遮罩通話、撥打電話及開始會議。</span><span class="sxs-lookup"><span data-stu-id="183a6-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="183a6-128">您可能會尋找另一個名稱相似的功能，即 Lync 行事曆委派。</span><span class="sxs-lookup"><span data-stu-id="183a6-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="183a6-129">它不需要企業語音功能，且允許使用者從 Outlook 排程線上 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="183a6-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="183a6-130">如果您在這裡找到該資訊，我們建議您檢查<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">CsClientPolicy</A> ，瞭解啟用 Exchange 委派同步處理的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="183a6-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="183a6-131">團隊通話可讓使用者同時撥打小組電話，讓小組中的任何人都能接聽通話。</span><span class="sxs-lookup"><span data-stu-id="183a6-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="183a6-132">[群組通話]： Lync Server 2013 的累積更新中的新功能：2013年2月，讓使用者從自己的手機向其同事接聽來電。</span><span class="sxs-lookup"><span data-stu-id="183a6-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="183a6-133">[群組呼叫挑選] 與小組通話的不同之處，主要是在預期收件者的手機上，僅限來電響鈴，但任何其他使用者都可以撥打電話挑選群組號碼，選擇接聽電話。</span><span class="sxs-lookup"><span data-stu-id="183a6-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="183a6-134">您可以設定回應群組，將呼叫路由及智慧地路由到指定的 agent。</span><span class="sxs-lookup"><span data-stu-id="183a6-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="183a6-135">常見用途包括 IT 提供人員、人力資源 hotlines，以及其他內部連絡人中心。</span><span class="sxs-lookup"><span data-stu-id="183a6-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="183a6-136">企業語音管理</span><span class="sxs-lookup"><span data-stu-id="183a6-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="183a6-137">Lync Server 使用標準與已發佈介面，與現有的基礎結構互動。</span><span class="sxs-lookup"><span data-stu-id="183a6-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="183a6-138">它支援閘道和 SIP 選項（例如 SIP 中繼），以便與 IP PBX 系統和 PSTN 網路進行互連，因此您可以在一段時間內將使用者遷移至企業語音，同時將中斷降至最低。</span><span class="sxs-lookup"><span data-stu-id="183a6-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="183a6-139">Lync Server 支援傳統的編解碼器，例如711、722和723.1，以實現與傳統 VoIP 解決方案的互通性。</span><span class="sxs-lookup"><span data-stu-id="183a6-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="183a6-140">系統管理員可以使用 [呼叫許可控制] （CAC）來設定受限制網路連結上的 Lync Server 語音及影片流量限制，並指定新呼叫超過限制時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="183a6-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="183a6-141">這些動作可能包括依備用路徑進行路由，或拒絕通話。</span><span class="sxs-lookup"><span data-stu-id="183a6-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="183a6-142">Lync Server 與協力廠商 Survivable 分支裝置搭配使用，以提供本機呼叫服務，以及分支辦公室的 PSTN 連線（在中央網站發生 WAN 故障時）。</span><span class="sxs-lookup"><span data-stu-id="183a6-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

