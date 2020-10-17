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
ms.openlocfilehash: 39179f1db1c547081e059d9b3ee275c924621cab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533170"
---
# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4a735-102">Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="4a735-102">Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a735-103">_**主題上次修改日期：** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="4a735-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="4a735-104">透過 Enterprise Voice，Lync Server 會提供獨立的語音 over 網際網路通訊協定 (VoIP) 可強化或更換傳統專用交換機 (PBX) 系統的產品。</span><span class="sxs-lookup"><span data-stu-id="4a735-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="4a735-105">Enterprise Voice 使用者可以撥打組織 VoIP 網路或 PBX 上的同事，也可以撥打組織外部的傳統電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4a735-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="4a735-106">Enterprise Voice 方案包含常見通話功能（例如，答案、轉寄、轉移、保留、轉移、發行和寄存）及增強型 9-1-1 (E9-1-1) 呼叫 (E9-1-1 只適用于美國。 ) Enterprise Voice 也支援廣泛的現有和 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="4a735-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="4a735-107">撥打和接聽電話</span><span class="sxs-lookup"><span data-stu-id="4a735-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="4a735-108">使用 Lync 時，使用者可以在鍵盤上輸入名稱或電話號碼，或使用螢幕上顯示的撥號鍵，以撥打通話。</span><span class="sxs-lookup"><span data-stu-id="4a735-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="4a735-109">使用者也可以直接從連絡人清單中初始化通話。</span><span class="sxs-lookup"><span data-stu-id="4a735-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="4a735-110">您也可以部署 Lync Phone Edition 裝置，這是 Microsoft 合作夥伴提供的獨立 IP 電話裝置。</span><span class="sxs-lookup"><span data-stu-id="4a735-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="4a735-111">使用者可以讓多個電話裝置向 Lync Server 註冊，而且可以輕鬆地進行切換。</span><span class="sxs-lookup"><span data-stu-id="4a735-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="4a735-112">使用者可在其所有裝置上同時收到來電，並可自訂的鈴聲于 IP 電話裝置上，以及類似于電腦上的立即訊息的通知。</span><span class="sxs-lookup"><span data-stu-id="4a735-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="4a735-113">使用者也可以設定一部電話號碼，以連線至其所在的電話、電腦和行動電話，所以不論身處何地，都可以到達。</span><span class="sxs-lookup"><span data-stu-id="4a735-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="4a735-114">基本通話功能</span><span class="sxs-lookup"><span data-stu-id="4a735-114">Basic Call Features</span></span>

<span data-ttu-id="4a735-115">在通話時，使用者可以接聽其他來電或發起撥出電話，而且現有的使用中通話會自動保留。</span><span class="sxs-lookup"><span data-stu-id="4a735-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="4a735-116">呼叫可以從某位使用者轉移到另一個使用者，不論是在第一位使用者私下使用第二位使用者的演講中。</span><span class="sxs-lookup"><span data-stu-id="4a735-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="4a735-117">使用者也可以將來電轉接至另一個裝置;例如，他們可以將使用中的來電轉接到行動電話，因為他們會向外移動他們的辦公室。</span><span class="sxs-lookup"><span data-stu-id="4a735-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="4a735-118">更豐富的通訊</span><span class="sxs-lookup"><span data-stu-id="4a735-118">Richer Communications</span></span>

<span data-ttu-id="4a735-119">當您使用 Lync 與其他使用者交談時，使用者可以輕鬆地將文字、影片或桌面共用新增至通話。</span><span class="sxs-lookup"><span data-stu-id="4a735-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="4a735-120">[請勿打擾] 功能會與 Lync 中的目前狀態設定整合。</span><span class="sxs-lookup"><span data-stu-id="4a735-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="4a735-121">使用 Exchange 整合通訊 (UM) ，Lync 和 Lync Server 會與 Microsoft Exchange Server 2013 和 Microsoft Outlook 2013 整合。</span><span class="sxs-lookup"><span data-stu-id="4a735-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="4a735-122">使用者可以查看他們的 Lync 視窗和電子郵件中是否有新的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4a735-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="4a735-123">在電子郵件中，他們可以按一下以在電子郵件訊息中播放語音信箱音訊，或是查看語音信箱訊息的成績單。</span><span class="sxs-lookup"><span data-stu-id="4a735-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="4a735-124">高級通話功能</span><span class="sxs-lookup"><span data-stu-id="4a735-124">Advanced Calling Features</span></span>

<span data-ttu-id="4a735-125">Enterprise Voice 也包含數種高級通話功能，例如 Lync 呼叫委派、小組通話、群組通話收取及回應群組。</span><span class="sxs-lookup"><span data-stu-id="4a735-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="4a735-126">Lync 呼叫委派可讓使用者將通話處理委派給一或多個助理，方法是移至 [ **工具**] \> **選項**「 \> **來電轉接設定**」。</span><span class="sxs-lookup"><span data-stu-id="4a735-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="4a735-127">代理人可代表使用者執行多個呼叫工作，包括篩選通話、撥出通話，以及發起會議。</span><span class="sxs-lookup"><span data-stu-id="4a735-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a735-128">您可能正在尋找其他具有類似名稱的功能，例如 Lync 行事曆委派。</span><span class="sxs-lookup"><span data-stu-id="4a735-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="4a735-129">不需要企業語音功能，也不允許使用者從 Outlook 排程線上 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="4a735-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="4a735-130">如果您已在這裡尋找該資訊，建議您取出 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> ，以取得啟用 Exchange 委派同步處理的資訊。</span><span class="sxs-lookup"><span data-stu-id="4a735-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="4a735-131">小組通話可讓使用者同時撥打小組電話，讓小組中的任何人都可以接聽通話。</span><span class="sxs-lookup"><span data-stu-id="4a735-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="4a735-132">群組呼叫收取（Lync Server 2013 的累計更新中的新功能：2月2013）可讓使用者從自己的電話接聽來電給其同事。</span><span class="sxs-lookup"><span data-stu-id="4a735-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="4a735-133">群組呼叫收取的不同之處在于，小組來電主要是在預期的收件者的電話上進行來電振鈴，但任何其他使用者可以撥打通話收取群組號碼來選擇回復。</span><span class="sxs-lookup"><span data-stu-id="4a735-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="4a735-134">回應群組可以設定為進行佇列，並智慧地將通話路由傳送至指定的代理人。</span><span class="sxs-lookup"><span data-stu-id="4a735-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="4a735-135">常見的使用包括 IT 人員服務中心、人力資源 hotlines 及其他內部連絡人中心。</span><span class="sxs-lookup"><span data-stu-id="4a735-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="4a735-136">Enterprise Voice Administration</span><span class="sxs-lookup"><span data-stu-id="4a735-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="4a735-137">Lync Server 會使用標準及發行的介面與現有基礎結構互動。</span><span class="sxs-lookup"><span data-stu-id="4a735-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="4a735-138">它支援閘道和 SIP 選項 (例如 SIP 主幹) ，以與 IP PBX 系統和 PSTN 網路進行互連，因此您可以將使用者遷移至 Enterprise Voice，但會使中斷降到最低。</span><span class="sxs-lookup"><span data-stu-id="4a735-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="4a735-139">Lync Server 支援傳統的編碼解碼器，例如 g.711、g.722 和 g.723.1，以與傳統的 VoIP 解決方案交互操作。</span><span class="sxs-lookup"><span data-stu-id="4a735-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="4a735-140">透過「通話許可控制」 (CAC) ，管理員可以設定受限制網路連結上的 Lync Server 語音和影片流量的數量限制，以及指定當新呼叫超出限制時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="4a735-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="4a735-141">動作可能包括透過替代路徑來路由傳送，或拒絕通話。</span><span class="sxs-lookup"><span data-stu-id="4a735-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="4a735-142">Lync Server 與協力廠商 Survivable 分支裝置搭配使用，以提供本機呼叫服務，並在分支辦公室連接至 PSTN，以在中央網站發生 WAN 失敗。</span><span class="sxs-lookup"><span data-stu-id="4a735-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

