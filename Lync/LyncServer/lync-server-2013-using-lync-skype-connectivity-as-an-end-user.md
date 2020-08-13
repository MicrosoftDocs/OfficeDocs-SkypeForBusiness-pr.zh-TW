---
title: Lync Server 2013：使用 Lync-Skype 連線能力做為使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6971ef2d6fb08838a4fcf71f4fec8097a7f9e47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="e599f-102">在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者</span><span class="sxs-lookup"><span data-stu-id="e599f-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e599f-103">_**主題上次修改日期：** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="e599f-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="e599f-104">Lync-Skype 連線功能可讓 Skype 使用者和 Lync 使用者將彼此新增為連絡人、exchange 立即訊息和進行音訊和視頻通話。</span><span class="sxs-lookup"><span data-stu-id="e599f-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="e599f-105">當 Skype 使用者新增 Lync 使用者時，Skype 使用者將在包含會話初始通訊協定 (SIP) 統一資源識別項 (URI) 的 Lync 使用者上建立連絡人。</span><span class="sxs-lookup"><span data-stu-id="e599f-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="e599f-106">相反地，當 Lync 使用者新增 Skype 連絡人時，lync 使用者會在 Lync 中建立連絡人，該連絡人會包含 Skype 使用者 (MSA) 中的 Microsoft 帳戶，而不是 Skype 使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="e599f-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="e599f-107">**什麼是 MSA？**</span><span class="sxs-lookup"><span data-stu-id="e599f-107">**What is an MSA?**</span></span> <span data-ttu-id="e599f-108">Skype 使用者必須使用 Microsoft 帳戶登入 Skype (先前稱為 Windows Live ID) ，才能與 Lync 連絡人進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e599f-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="e599f-109">Microsoft 帳戶包含電子郵件地址和密碼的組合，您也可以用來登入服務，例如 Microsoft OneDrive 儲存技術、Windows Phone、Microsoft Xbox LIVE online 遊戲服務，以及 Microsoft Outlook 郵件和共同作業用戶端 (，但先前是 Microsoft Hotmail web 電子郵件服務或 Windows Live Messenger) 。</span><span class="sxs-lookup"><span data-stu-id="e599f-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="e599f-110">如果您使用電子郵件地址和密碼來登入這些或其他服務，您已有 Microsoft 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e599f-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="e599f-111">如需建立 Microsoft 帳戶的詳細資訊，請參閱中的 Microsoft 帳戶註冊頁面 [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) 。</span><span class="sxs-lookup"><span data-stu-id="e599f-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="e599f-112">您可以在各種應用程式和服務中，將現有的 Skype 帳戶與 Microsoft 帳戶搭配使用，以進行單一登入。</span><span class="sxs-lookup"><span data-stu-id="e599f-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="e599f-113">在合併帳戶後，Skype 使用者可以將連絡人要求傳送至 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="e599f-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e599f-114">為了讓 Lync 和 Skype 使用者完全相互通訊，必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="e599f-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e599f-115">Skype 使用者必須使用 Microsoft 帳戶登入其 Skype 用戶端 (MSA) 。</span><span class="sxs-lookup"><span data-stu-id="e599f-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="e599f-116">Lync 使用者必須啟用其 Lync 系統管理員的公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="e599f-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="e599f-117">當 Skype 使用者新增 Lync 連絡人時，請確認 word Lync 出現在連絡人的名稱下方。</span><span class="sxs-lookup"><span data-stu-id="e599f-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="e599f-118">這表示已找到 Lync URI。</span><span class="sxs-lookup"><span data-stu-id="e599f-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="e599f-119">當 Skype 使用者新增 Lync 連絡人，且為該 Lync 網域傳回零搜尋結果時，PIC 布建處理常式可能尚未完成，或 Lync 網域尚未設定。</span><span class="sxs-lookup"><span data-stu-id="e599f-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="e599f-120">根據 Lync 和 Skype 使用者的隱私權設定，IM、影片及顯示狀態可能無法運作，直到每位使用者都接受新的連絡人為止。</span><span class="sxs-lookup"><span data-stu-id="e599f-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="e599f-121">**若要將 Skype 連絡人新增至 Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="e599f-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="e599f-122">從 Lync，按一下 [ **新增連絡人]，新增「我的組織」以外的連絡人**。</span><span class="sxs-lookup"><span data-stu-id="e599f-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="e599f-123">從可用的連絡人提供者清單中，選取 [ **Skype**]。</span><span class="sxs-lookup"><span data-stu-id="e599f-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="e599f-124">在 [ **IM 位址** ] 欄位中，輸入 Microsoft 帳戶 (的 Skype 使用者的 MSA) 。</span><span class="sxs-lookup"><span data-stu-id="e599f-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="e599f-125">在 [ **新增至連絡人群組** ] 下拉式方塊中，選取要新增使用者的連絡人群組。</span><span class="sxs-lookup"><span data-stu-id="e599f-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="e599f-126">在 [ **設定隱私權關聯** ] 下拉式清單方塊中，選取適當的連絡人設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e599f-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="e599f-127">使用者現在會顯示為 Lync 中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="e599f-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="e599f-128">選取使用者，在使用者名稱上按一下滑鼠右鍵，然後按一下 [ **請參閱連絡人卡片** ] 以查看使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="e599f-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="e599f-129">您現在可以使用新加入的 Skype 使用者建立音訊或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="e599f-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="e599f-130">如需有關連絡人支援的詳細資訊，請參閱 [在 Lync 新增連絡人](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)。</span><span class="sxs-lookup"><span data-stu-id="e599f-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="e599f-131">當 Skype 使用者的 Microsoft 帳戶使用自訂的功能變數名稱（例如 <strong>bob@contoso.com</strong> ），lync 使用者可以使用兩種方式將該 Microsoft 帳戶新增至 Lync：</span><span class="sxs-lookup"><span data-stu-id="e599f-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="e599f-132">使用 [ **新增連絡人** ] 圖示，或</span><span class="sxs-lookup"><span data-stu-id="e599f-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="e599f-133">使用 [ **尋找某人或會議室] 或 [撥打號碼** ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="e599f-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="e599f-134">在每個實例中，Lync 使用者必須以下列格式輸入 Skype 使用者的電子郵件： <strong>使用者 (功能變數名稱) @msn .com</strong> 。</span><span class="sxs-lookup"><span data-stu-id="e599f-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e599f-135">使用下列功能變數名稱的 Microsoft 帳戶，不需要此步驟： <STRONG>@live .com、@hotmail .com 或 @outlook .com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e599f-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="e599f-136">如需支援的自訂功能變數名稱的詳細資訊，請參閱 <A href="https://support.microsoft.com/kb/897567">支援的公用 IM 網域</A>。</span><span class="sxs-lookup"><span data-stu-id="e599f-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="e599f-137">**使用自訂功能變數名稱將 Skype 連絡人新增至 Lync**</span><span class="sxs-lookup"><span data-stu-id="e599f-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="e599f-138">從 Lync，按一下 [ **新增連絡人]，新增「我的組織」以外的連絡人**。</span><span class="sxs-lookup"><span data-stu-id="e599f-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="e599f-139">從可用的連絡人提供者清單中，選取 [ **Skype**]。</span><span class="sxs-lookup"><span data-stu-id="e599f-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="e599f-140">在 [ **IM 位址** ] 欄位中，以 <strong>使用者 @msn) 名稱 (功能變數名稱</strong> (MSA) ，輸入 Microsoft 帳戶 MSA。</span><span class="sxs-lookup"><span data-stu-id="e599f-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="e599f-141">因此，針對使用者 bob@contoso.com，該專案會是 <strong> 小明 (contoso.com) @msn .com <strong> 。</span><span class="sxs-lookup"><span data-stu-id="e599f-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="e599f-142">在 [ **新增至連絡人群組** ] 下拉式清單方塊中，選取要新增使用者的連絡人群組。</span><span class="sxs-lookup"><span data-stu-id="e599f-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="e599f-143">在 [ **設定隱私權關聯** ] 下拉式清單方塊中，選取適當的連絡人設定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e599f-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="e599f-144">Lync 使用者也可以使用 [ **尋找某人或會議室]，或** 在 Lync 中撥打號碼欄位，並新增類似下列 <strong>使用者 (功能變數名稱) @msn .com</strong> 的位址。</span><span class="sxs-lookup"><span data-stu-id="e599f-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="e599f-145">所以針對 bob@contoso.com Microsoft 帳戶，此專案會是 <strong>王俊元 (contoso.com) @msn .com</strong> 。</span><span class="sxs-lookup"><span data-stu-id="e599f-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="e599f-146">遵循此程式前面的步驟4和5，將連絡人新增至連絡人群組，並選取適當的隱私權關聯。</span><span class="sxs-lookup"><span data-stu-id="e599f-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="e599f-147">**若要將 Lync 連絡人新增至 Skype**</span><span class="sxs-lookup"><span data-stu-id="e599f-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="e599f-148">登入 Skype。</span><span class="sxs-lookup"><span data-stu-id="e599f-148">Sign in to Skype.</span></span> <span data-ttu-id="e599f-149">Skype 使用者必須使用 Microsoft 帳戶登入其 Skype 用戶端 (MSA) 。</span><span class="sxs-lookup"><span data-stu-id="e599f-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="e599f-150">選取 [新增連絡人] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e599f-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="e599f-151">輸入 Lync 使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="e599f-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="e599f-152">例如，bob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e599f-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="e599f-153">當 Skype 發現搜尋結果中的相符時，請尋找 Lync 使用者名稱下方的 [ **lync** ] 字樣。</span><span class="sxs-lookup"><span data-stu-id="e599f-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="e599f-154">這表示 Skype 成功找到 Lync 用戶端的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="e599f-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="e599f-155">按一下名稱。</span><span class="sxs-lookup"><span data-stu-id="e599f-155">Click the name.</span></span>

5.  <span data-ttu-id="e599f-156">在視窗的右上角，按一下 [新增至連絡人]。</span><span class="sxs-lookup"><span data-stu-id="e599f-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="e599f-157">新連絡人現在已新增至您的連絡人清單，但您會看到一個問號，而不是其狀態圖示，直到他們接受您的要求為止。</span><span class="sxs-lookup"><span data-stu-id="e599f-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="e599f-158">當您的新連絡人接受您的要求時，您將能夠看到他們線上時、發起 IM 交談，以及進行音訊和視頻通話。</span><span class="sxs-lookup"><span data-stu-id="e599f-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e599f-159">Lync Server 管理員必須設定 Lync 使用者的原則設定，以允許傳入要求。</span><span class="sxs-lookup"><span data-stu-id="e599f-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="e599f-160">否則，Lync 使用者將不會收到來自 Skype 使用者的連絡人要求。</span><span class="sxs-lookup"><span data-stu-id="e599f-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="e599f-161">根據 Lync 使用者原則設定的設定，加入 Skype 使用者的要求會出現在 Lync 用戶端的 [ <STRONG>新增</STRONG> ] 索引標籤上。若要開始與 Skype 使用者通訊，Lync 使用者必須將 Skype 使用者新增至 [我的最愛] 清單或連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="e599f-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="e599f-162">下圖顯示 Lync 用戶端中 [ <STRONG>新增</STRONG> ] 索引標籤的位置。</span><span class="sxs-lookup"><span data-stu-id="e599f-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="e599f-163">Lync 使用者必須設定 Lync 警示，以確保 Lync 使用者傳送的要求出現，而且可由 Lync 使用者探索。</span><span class="sxs-lookup"><span data-stu-id="e599f-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="e599f-164">若要設定 Lync 提醒，請完成下列程式。</span><span class="sxs-lookup"><span data-stu-id="e599f-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="e599f-165">**設定 Lync 提醒**</span><span class="sxs-lookup"><span data-stu-id="e599f-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="e599f-166">在 Lync 用戶端中，按一下 [ **選項** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e599f-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="e599f-167">選取 [ **警示**]。</span><span class="sxs-lookup"><span data-stu-id="e599f-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="e599f-168">在 **[一般提醒**] 底下，選取 [ **當某人將我加入連絡人清單時，請告訴我**]。</span><span class="sxs-lookup"><span data-stu-id="e599f-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="e599f-169">在 [ **不使用 Lync 的連絡人**] 底下，選取 [ **允許邀請，但封鎖所有其他通訊**]。</span><span class="sxs-lookup"><span data-stu-id="e599f-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="e599f-170">按一下 **[確定** ] 關閉 [選項] 視窗。</span><span class="sxs-lookup"><span data-stu-id="e599f-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

