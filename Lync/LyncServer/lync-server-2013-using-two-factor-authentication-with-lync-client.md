---
title: Lync Server 2013：搭配 Lync 用戶端使用雙因素驗證
description: Lync Server 2013：搭配 Lync 用戶端使用雙要素驗證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfde1d04d4e641c8fbe4817ffce214df891b565
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547279"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="845ee-103">使用 Lync 用戶端和 Lync Server 2013 的雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="845ee-103">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="845ee-104">_**主題上次修改日期：** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="845ee-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="845ee-105">本主題說明如何利用 Lync 2013 用戶端的雙要素驗證。</span><span class="sxs-lookup"><span data-stu-id="845ee-105">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="845ee-106">第一次登入 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="845ee-106">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="845ee-107">您的 Lync 登錄資訊通常會在安裝 Lync 2013 時自動設定。</span><span class="sxs-lookup"><span data-stu-id="845ee-107">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="845ee-108">不過，您第一次使用 Lync 時，您可能需要手動啟動用戶端。</span><span class="sxs-lookup"><span data-stu-id="845ee-108">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="845ee-109">**第一次登入 Lync**</span><span class="sxs-lookup"><span data-stu-id="845ee-109">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="845ee-110">登入您組織的網路。</span><span class="sxs-lookup"><span data-stu-id="845ee-110">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="845ee-111">選取 [ **啟動** \> **所有程式**] [ \> **Microsoft Lync \> lync 2013**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-111">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="845ee-112">您應該會看到 [Lync 登錄] 畫面。</span><span class="sxs-lookup"><span data-stu-id="845ee-112">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="845ee-113">如果 [登入位址] 方塊已經填入，請確認顯示的位址正確無誤。</span><span class="sxs-lookup"><span data-stu-id="845ee-113">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="845ee-114">如果不正確，或如果方塊是空的，請輸入您的 Lync 登入位址 (這通常與您的電子郵件地址) 相同。</span><span class="sxs-lookup"><span data-stu-id="845ee-114">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="845ee-115">如果顯示 [空白密碼] 方塊，請新增您的密碼。</span><span class="sxs-lookup"><span data-stu-id="845ee-115">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="845ee-116">選取 [登 **入**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-116">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="845ee-117">登出 Lync</span><span class="sxs-lookup"><span data-stu-id="845ee-117">Sign out of Lync</span></span>

<span data-ttu-id="845ee-118">當您完成使用 Lync 時，您可以從 [檔案] 功能表中關閉顯示、登出您的會話或從程式退出。</span><span class="sxs-lookup"><span data-stu-id="845ee-118">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="845ee-119">下表說明選項的差異。</span><span class="sxs-lookup"><span data-stu-id="845ee-119">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="845ee-120">選項</span><span class="sxs-lookup"><span data-stu-id="845ee-120">Option</span></span></th>
<th><span data-ttu-id="845ee-121">其用途</span><span class="sxs-lookup"><span data-stu-id="845ee-121">What it does</span></span></th>
<th><span data-ttu-id="845ee-122">執行方法</span><span class="sxs-lookup"><span data-stu-id="845ee-122">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="845ee-123">關閉</span><span class="sxs-lookup"><span data-stu-id="845ee-123">Close</span></span></p></td>
<td><p><span data-ttu-id="845ee-124">關閉您的 Lync 顯示器，但讓識別了您的使用者識別碼的 Lync 會話繼續執行。</span><span class="sxs-lookup"><span data-stu-id="845ee-124">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="845ee-125">如此一來，您就可以繼續取得通知並與其他人互動。</span><span class="sxs-lookup"><span data-stu-id="845ee-125">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="845ee-126">您可以隨時按一下工作列上的 Lync 圖示或螢幕底部的通知區域，以取回顯示。</span><span class="sxs-lookup"><span data-stu-id="845ee-126">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="845ee-127">在 Lync 主視窗中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="845ee-127">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="845ee-128">選取 [ <strong>選項</strong> ] 按鈕，然後選取 [ <strong>檔</strong> &gt; <strong>關閉</strong>]。</span><span class="sxs-lookup"><span data-stu-id="845ee-128">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="845ee-129">按一下視窗右上角 (X) 中的 [ <strong>關閉</strong> ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="845ee-129">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="845ee-130">登出</span><span class="sxs-lookup"><span data-stu-id="845ee-130">Sign out</span></span></p></td>
<td><p><span data-ttu-id="845ee-131">結束與您的使用者識別碼相關聯的 Lync 會話，但是 Lync 會繼續在後臺執行。</span><span class="sxs-lookup"><span data-stu-id="845ee-131">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="845ee-132">當您登出時，即會出現登入視窗。</span><span class="sxs-lookup"><span data-stu-id="845ee-132">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="845ee-133">當您登出時，請選取 [ <STRONG>刪除我的登入資訊</STRONG> ]，以移除電腦上的登入識別碼和密碼記錄。</span><span class="sxs-lookup"><span data-stu-id="845ee-133">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="845ee-134">這樣做可能會讓支援人員更容易疑難排解登入問題。</span><span class="sxs-lookup"><span data-stu-id="845ee-134">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="845ee-135">它也可以讓未經授權的使用者難以登入您的認證，以協助確保您的登入資訊更安全。</span><span class="sxs-lookup"><span data-stu-id="845ee-135">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="845ee-136">在 Lync 主視窗中，選取 [ <strong>選項</strong> ] 按鈕，然後 <strong>選取 [</strong>檔案] [ &gt; <strong>登出</strong>]。</span><span class="sxs-lookup"><span data-stu-id="845ee-136">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="845ee-137">結束</span><span class="sxs-lookup"><span data-stu-id="845ee-137">Exit</span></span></p></td>
<td><p><span data-ttu-id="845ee-138">結束您的 Lync 會話，並關閉您電腦上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="845ee-138">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="845ee-139">退出後，如果您想要重新開機 Lync，請選取 [ <strong>啟動</strong> &gt; <strong>所有程式</strong>] [ &gt; <strong>Microsoft Lync</strong> &gt; <strong>lync 2013</strong>]。</span><span class="sxs-lookup"><span data-stu-id="845ee-139">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="845ee-140">在 Lync 主視窗中，選取 [ <strong>選項</strong> ] 按鈕，然後 <strong>選取 [</strong>檔案] [結束] &gt; <strong> </strong>。</span><span class="sxs-lookup"><span data-stu-id="845ee-140">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="845ee-141">使用智慧卡登入 Lync</span><span class="sxs-lookup"><span data-stu-id="845ee-141">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="845ee-142">有些組織現在會使用多步驟登入處理常式（稱為二要素驗證），以提升其 Lync 2013 使用者的安全性。</span><span class="sxs-lookup"><span data-stu-id="845ee-142">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="845ee-143">如果您想要使用此選項，則需要 "智慧卡" 才能登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="845ee-143">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="845ee-144">智慧卡分為兩種種類、實體和虛擬：</span><span class="sxs-lookup"><span data-stu-id="845ee-144">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="845ee-145">**實體**    關於信用卡的大小。</span><span class="sxs-lookup"><span data-stu-id="845ee-145">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="845ee-146">當您登入時，您可以將它插入智慧卡讀取器。</span><span class="sxs-lookup"><span data-stu-id="845ee-146">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="845ee-147">**虛擬**    不是實體物件，而是寫入電腦上的特殊晶片的電子識別碼，實際上是在電腦上建立智慧卡。</span><span class="sxs-lookup"><span data-stu-id="845ee-147">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="845ee-148">僅適用于包含 TPM (信任的平臺模組) 晶片的 Windows 8 電腦。</span><span class="sxs-lookup"><span data-stu-id="845ee-148">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="845ee-149">註冊您的智慧卡</span><span class="sxs-lookup"><span data-stu-id="845ee-149">Enroll your smart card</span></span>

<span data-ttu-id="845ee-150">在您可以使用智慧卡登入時，必須先「登記」智慧卡，也就是您的使用者認證必須透過卡片加以識別。</span><span class="sxs-lookup"><span data-stu-id="845ee-150">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="845ee-151">這種情況是由卡為實體或虛擬的情形所決定。</span><span class="sxs-lookup"><span data-stu-id="845ee-151">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="845ee-152">您的 Lync Server 系統管理員可能已執行此程式。</span><span class="sxs-lookup"><span data-stu-id="845ee-152">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="845ee-153">如果您不確定是否已完成，請與其核對。</span><span class="sxs-lookup"><span data-stu-id="845ee-153">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="845ee-154">因為每個虛擬智慧卡只會與其安裝裝置相關聯，所以需要為您使用的每一部 Windows 8 電腦登記個別的卡。</span><span class="sxs-lookup"><span data-stu-id="845ee-154">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="845ee-155">**手動註冊您的智慧卡**</span><span class="sxs-lookup"><span data-stu-id="845ee-155">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="845ee-156">登入您要執行 Lync 的電腦。</span><span class="sxs-lookup"><span data-stu-id="845ee-156">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="845ee-157">使用 Internet Explorer，流覽至組織的 [憑證授權單位網站] [註冊] 頁面。</span><span class="sxs-lookup"><span data-stu-id="845ee-157">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="845ee-158">如果您還沒有這個資源的網址，請詢問您的 Lync Server 管理員。</span><span class="sxs-lookup"><span data-stu-id="845ee-158">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="845ee-159">URL 看起來像這樣： https://MyCA.\ [yourcompanyname \] .com/certsrv。</span><span class="sxs-lookup"><span data-stu-id="845ee-159">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="845ee-160">如果您使用的是 Internet Explorer 10，您可能需要在相容性模式中查看此網站。</span><span class="sxs-lookup"><span data-stu-id="845ee-160">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="845ee-161">當系統提示您登入憑證頁面時，請使用您的網域帳戶登入 (，而不是) 的電腦系統管理員。</span><span class="sxs-lookup"><span data-stu-id="845ee-161">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="845ee-162">在 [網站歡迎] 頁面上，選取 [ **要求憑證**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-162">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="845ee-163">選取 [ **高級要求**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-163">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="845ee-164">選取 [ **建立並提交此 CA 的要求**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="845ee-164">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="845ee-165">現在，您會看到一個稱為智慧卡註冊站的頁面。</span><span class="sxs-lookup"><span data-stu-id="845ee-165">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="845ee-166">核准要求以安裝 ActiveX 控制項，然後完成 [高級憑證要求] 表單，如下所示：</span><span class="sxs-lookup"><span data-stu-id="845ee-166">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="845ee-167">從 [**憑證範本**] 下拉式清單中選取 [**智慧卡使用者**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="845ee-168">選取 [ **建立新的金鑰集**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-168">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="845ee-169">在智慧卡標籤上尋找廠商資訊，然後從 **CSP** 下拉式清單中選取該廠商。</span><span class="sxs-lookup"><span data-stu-id="845ee-169">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="845ee-170">選取 [ **CSP** ] 做為要求格式（如果尚未選取）。</span><span class="sxs-lookup"><span data-stu-id="845ee-170">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="845ee-171">從 [雜湊演算法] 下拉式清單中選取 [ **sha1** ] （如果尚未選取）。</span><span class="sxs-lookup"><span data-stu-id="845ee-171">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="845ee-172">將您要識別的憑證命名為 [名稱]，然後按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-172">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="845ee-173">現在，將空白智慧卡插入附加至註冊站的讀卡機，然後按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-173">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="845ee-174">出現提示時，請輸入您的個人身分識別號碼 (PIN) ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="845ee-174">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="845ee-175">如果您的技術支援人員未提供您用來註冊智慧卡的特殊 PIN 碼，請使用預設的智慧卡 PIN 碼值，也就是12345678。</span><span class="sxs-lookup"><span data-stu-id="845ee-175">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="845ee-176">選取此選項，可強制使用者在第一次使用智慧卡時) 變更 PIN (。</span><span class="sxs-lookup"><span data-stu-id="845ee-176">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="845ee-177">現在，將空白智慧卡插入附加至註冊站的讀卡機，然後按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-177">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="845ee-178">出現提示時，請輸入您的個人身分識別號碼 (PIN) ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="845ee-178">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="845ee-179">如果您的技術支援人員未提供您用來註冊智慧卡的特殊 PIN 碼，請使用預設的智慧卡 PIN 碼值，也就是12345678。</span><span class="sxs-lookup"><span data-stu-id="845ee-179">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="845ee-180">選取此選項，可強制使用者在第一次使用智慧卡時) 變更 PIN (。</span><span class="sxs-lookup"><span data-stu-id="845ee-180">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="845ee-181">按一下 **[確定]** ，確認顯示的憑證有其資訊。</span><span class="sxs-lookup"><span data-stu-id="845ee-181">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="845ee-182">當您看到已簽發憑證的通知之後，按一下 [ **安裝此憑證** ] 以完成註冊程式。</span><span class="sxs-lookup"><span data-stu-id="845ee-182">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="845ee-183">使用智慧卡認證登入 Lync</span><span class="sxs-lookup"><span data-stu-id="845ee-183">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="845ee-184">在您第一次使用智慧卡之前，建議您在 Lync 登入頁面上按一下 [ **刪除我的登入資訊** ]。</span><span class="sxs-lookup"><span data-stu-id="845ee-184">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="845ee-185">這樣做會清除儲存在電腦上的任何登入認證，並消除可能的錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="845ee-185">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="845ee-186">**使用智慧卡認證登入 Lync**</span><span class="sxs-lookup"><span data-stu-id="845ee-186">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="845ee-187">啟動 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="845ee-187">Start the Lync client.</span></span>

2.  <span data-ttu-id="845ee-188">在 [登入] 畫面的 [登 **入位址** ] 方塊中，輸入您的登入使用者帳戶名稱，然後按一下 [登 **入**]。</span><span class="sxs-lookup"><span data-stu-id="845ee-188">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="845ee-189">如果您是使用虛擬智慧卡，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="845ee-189">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="845ee-190">如果您使用的是實體智慧卡，請將智慧卡插入智慧卡讀取器中，然後提示您執行此動作，然後在偵測到卡時按一下 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="845ee-190">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="845ee-191">輸入智慧卡的 PIN 碼號碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="845ee-191">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="845ee-192">如果您的支援人員未指派智慧卡 PIN 碼號碼，請使用預設值，也就是12345678。</span><span class="sxs-lookup"><span data-stu-id="845ee-192">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

