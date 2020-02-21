---
title: Lync Server 2013： 使用 Lync 用戶端使用雙因素驗證
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
ms.openlocfilehash: c90183d13581387d444301278d4c1c1125e5dc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="333cb-102">使用 Lync 用戶端和 Lync Server 2013 的雙因素驗證</span><span class="sxs-lookup"><span data-stu-id="333cb-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="333cb-103">_**上次修改主題：** 2013年-07-11_</span><span class="sxs-lookup"><span data-stu-id="333cb-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="333cb-104">本主題說明如何利用與 Lync 2013 用戶端的雙因素驗證。</span><span class="sxs-lookup"><span data-stu-id="333cb-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="333cb-105">第一次登入 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="333cb-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="333cb-106">安裝 Lync 2013 時，通常會自動設定您的 Lync 登入資訊。</span><span class="sxs-lookup"><span data-stu-id="333cb-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="333cb-107">但是，第一次您使用 Lync，您可能需要手動啟動用戶端。</span><span class="sxs-lookup"><span data-stu-id="333cb-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="333cb-108">**第一次登入 Lync**</span><span class="sxs-lookup"><span data-stu-id="333cb-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="333cb-109">登入您的組織網路。</span><span class="sxs-lookup"><span data-stu-id="333cb-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="333cb-110">選取 [**開始** \> **所有程式]** \> **Microsoft Lync \> Lync 2013**。</span><span class="sxs-lookup"><span data-stu-id="333cb-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="333cb-111">您應該會看到 Lync 登入畫面。</span><span class="sxs-lookup"><span data-stu-id="333cb-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="333cb-112">如果已填入登入位址] 方塊中，確認顯示的地址正確無誤。</span><span class="sxs-lookup"><span data-stu-id="333cb-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="333cb-113">如果不正確，或如果方塊為空白，輸入您 Lync 登入地址 （這通常是您的電子郵件地址相同）。</span><span class="sxs-lookup"><span data-stu-id="333cb-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="333cb-114">如果會顯示空白密碼] 方塊中，新增您的密碼。</span><span class="sxs-lookup"><span data-stu-id="333cb-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="333cb-115">選取 [**登入**。</span><span class="sxs-lookup"><span data-stu-id="333cb-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="333cb-116">登出 Lync</span><span class="sxs-lookup"><span data-stu-id="333cb-116">Sign out of Lync</span></span>

<span data-ttu-id="333cb-117">當您完成使用 Lync 時，您可以關閉顯示畫面中，登出您的工作階段，或結束的程式，所有從 [檔案] 功能表。</span><span class="sxs-lookup"><span data-stu-id="333cb-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="333cb-118">下表說明選項] 中的差異。</span><span class="sxs-lookup"><span data-stu-id="333cb-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333cb-119">Option</span><span class="sxs-lookup"><span data-stu-id="333cb-119">Option</span></span></th>
<th><span data-ttu-id="333cb-120">其用途</span><span class="sxs-lookup"><span data-stu-id="333cb-120">What it does</span></span></th>
<th><span data-ttu-id="333cb-121">若要執行它的方式</span><span class="sxs-lookup"><span data-stu-id="333cb-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333cb-122">關閉</span><span class="sxs-lookup"><span data-stu-id="333cb-122">Close</span></span></p></td>
<td><p><span data-ttu-id="333cb-123">會關閉 Lync 顯示，但可讓 Lync 工作階段識別您的使用者識別碼繼續執行。</span><span class="sxs-lookup"><span data-stu-id="333cb-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="333cb-124">這是讓您可以繼續取得通知，並與其他人互動。</span><span class="sxs-lookup"><span data-stu-id="333cb-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="333cb-125">您可以透過任何時候回顯示按一下工作列上或螢幕底部的 [通知] 區域上的 Lync 圖示。</span><span class="sxs-lookup"><span data-stu-id="333cb-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="333cb-126">在 Lync 主視窗中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="333cb-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="333cb-127">選取 [<strong>選項</strong>] 按鈕，然後選取 [<strong>檔案</strong> &gt; <strong>關閉</strong>。</span><span class="sxs-lookup"><span data-stu-id="333cb-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="333cb-128">視窗的右上角中，按一下 [<strong>關閉</strong>] 按鈕 (X)。</span><span class="sxs-lookup"><span data-stu-id="333cb-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333cb-129">登出</span><span class="sxs-lookup"><span data-stu-id="333cb-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="333cb-130">結束相關聯的使用者 ID，但 Lync Lync 工作階段繼續在背景執行。</span><span class="sxs-lookup"><span data-stu-id="333cb-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="333cb-131">當您登出時，會出現登入視窗。</span><span class="sxs-lookup"><span data-stu-id="333cb-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="333cb-132">當您登出，才能從電腦移除您的登入識別碼和密碼的記錄，請選取 [<STRONG>刪除我的登入資訊</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="333cb-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="333cb-133">這麼做可能會讓更容易登入問題進行疑難排解的支援人員。</span><span class="sxs-lookup"><span data-stu-id="333cb-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="333cb-134">它也可以協助確保您登入資訊是更安全者難以未經授權的使用者使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="333cb-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="333cb-135">在 Lync 主視窗中，選取 [<strong>選項</strong>] 按鈕，然後選取 [<strong>檔案</strong> &gt; <strong>登出</strong>。</span><span class="sxs-lookup"><span data-stu-id="333cb-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333cb-136">結束</span><span class="sxs-lookup"><span data-stu-id="333cb-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="333cb-137">會結束您的 Lync 工作階段，並關閉 Lync，在您的電腦上。</span><span class="sxs-lookup"><span data-stu-id="333cb-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="333cb-138">之後結束，如果您想要重新啟動 Lync，選取 [<strong>啟動</strong> &gt; <strong>所有程式]</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>。</span><span class="sxs-lookup"><span data-stu-id="333cb-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="333cb-139">在 Lync 主視窗中，選取 [<strong>選項</strong>] 按鈕，然後選取 [<strong>檔案</strong> &gt; <strong>結束</strong>。</span><span class="sxs-lookup"><span data-stu-id="333cb-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="333cb-140">登入 Lync 與智慧卡</span><span class="sxs-lookup"><span data-stu-id="333cb-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="333cb-141">現在，有些組織會使用多個步驟登入程序，稱為雙因素驗證，以增加其 Lync 2013 使用者的安全性。</span><span class="sxs-lookup"><span data-stu-id="333cb-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="333cb-142">如果您所預期，請使用此選項，您必須登入 Lync 」 智慧卡 」。</span><span class="sxs-lookup"><span data-stu-id="333cb-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="333cb-143">智慧卡會以兩個實體和虛擬的種類：</span><span class="sxs-lookup"><span data-stu-id="333cb-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="333cb-144">**實體**   有關信用卡的大小。</span><span class="sxs-lookup"><span data-stu-id="333cb-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="333cb-145">您將它插入智慧卡讀取時您登入。</span><span class="sxs-lookup"><span data-stu-id="333cb-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="333cb-146">**虛擬**   實體的物件，但您的電腦，藉以基本上智慧卡插入您的電腦的特殊晶片取得寫入電子識別碼。</span><span class="sxs-lookup"><span data-stu-id="333cb-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="333cb-147">僅適用於 Windows 8 電腦內含 TPM （信任的平台模組） 晶片搭配使用。</span><span class="sxs-lookup"><span data-stu-id="333cb-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="333cb-148">註冊您的智慧卡</span><span class="sxs-lookup"><span data-stu-id="333cb-148">Enroll your smart card</span></span>

<span data-ttu-id="333cb-149">您可以使用智慧卡登入前，卡必須 「 註冊 」，也就是必須卡用來識別您的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="333cb-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="333cb-150">實體或虛擬智慧卡是否，這會是這種情況。</span><span class="sxs-lookup"><span data-stu-id="333cb-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="333cb-151">此程序可能已經已取出您的 Lync Server 系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="333cb-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="333cb-152">如果您不確定是否會有已完成，請檢查與它們。</span><span class="sxs-lookup"><span data-stu-id="333cb-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="333cb-153">因為每個虛擬智慧卡是只與裝置相關聯上安裝，個別的卡片需要您使用每個 Windows 8 電腦上註冊。</span><span class="sxs-lookup"><span data-stu-id="333cb-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="333cb-154">**若要手動註冊您的智慧卡**</span><span class="sxs-lookup"><span data-stu-id="333cb-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="333cb-155">您會在執行 Lync 的電腦登入。</span><span class="sxs-lookup"><span data-stu-id="333cb-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="333cb-156">使用 Internet Explorer，瀏覽至您的組織憑證授權單位網頁註冊頁面。</span><span class="sxs-lookup"><span data-stu-id="333cb-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="333cb-157">如果您還沒有其此資源的網頁地址要求您的 Lync Server 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="333cb-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="333cb-158">URL 看起來像這樣： https://MyCA.\[yourcompanyname\].com/certsrv。</span><span class="sxs-lookup"><span data-stu-id="333cb-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="333cb-159">如果您使用 Internet Explorer 10，您可能需要在相容性模式中檢視此網站。</span><span class="sxs-lookup"><span data-stu-id="333cb-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="333cb-160">當系統提示您登入 [憑證] 頁面上時，記錄上使用您的網域帳戶 （而不是您電腦的系統管理員）。</span><span class="sxs-lookup"><span data-stu-id="333cb-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="333cb-161">在網站的歡迎使用] 頁面中，選取 [**要求憑證**]。</span><span class="sxs-lookup"><span data-stu-id="333cb-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="333cb-162">選取 [**進階要求**]。</span><span class="sxs-lookup"><span data-stu-id="333cb-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="333cb-163">選取 [**建立並送出要求至此 CA**，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="333cb-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="333cb-164">現在您會看到一個稱為智慧卡註冊站的頁面。</span><span class="sxs-lookup"><span data-stu-id="333cb-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="333cb-165">核准要求以安裝 ActiveX 控制項，並再完成其進階憑證要求表單，如下所示：</span><span class="sxs-lookup"><span data-stu-id="333cb-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="333cb-166">從 [**憑證範本**] 下拉式清單中選取**智慧卡使用者**。</span><span class="sxs-lookup"><span data-stu-id="333cb-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="333cb-167">選取 [**建立新的金鑰組**。</span><span class="sxs-lookup"><span data-stu-id="333cb-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="333cb-168">尋找您的智慧卡在標籤上的製造商資訊並從 [ **CSP** ] 下拉式清單中選取該製造商。</span><span class="sxs-lookup"><span data-stu-id="333cb-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="333cb-169">選取**雲端解決方案提供者**要求格式，如果尚未選取。</span><span class="sxs-lookup"><span data-stu-id="333cb-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="333cb-170">如果尚未選取，請從雜湊演算法] 下拉式清單中，選取**sha1** 。</span><span class="sxs-lookup"><span data-stu-id="333cb-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="333cb-171">授與您的憑證會辨識，並按一下 [**送出**的名稱。</span><span class="sxs-lookup"><span data-stu-id="333cb-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="333cb-172">現在您空白的智慧卡插入卡片讀者附加至註冊站，然後按一下 [**註冊**。</span><span class="sxs-lookup"><span data-stu-id="333cb-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="333cb-173">出現提示時，輸入您的個人識別碼 (PIN)，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="333cb-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="333cb-174">如果您的技術支援人員不提供已特殊的 pin 碼，以用於註冊您的智慧卡，使用預設智慧卡 pin 碼值，即 12345678。</span><span class="sxs-lookup"><span data-stu-id="333cb-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="333cb-175">選取 [強制使用者 （您） 若要變更使用智慧卡 PIN 第一次] 選項。</span><span class="sxs-lookup"><span data-stu-id="333cb-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="333cb-176">現在您空白的智慧卡插入卡片讀者附加至註冊站，然後按一下 [**註冊**。</span><span class="sxs-lookup"><span data-stu-id="333cb-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="333cb-177">出現提示時，輸入您的個人識別碼 (PIN)，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="333cb-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="333cb-178">如果您的技術支援人員不提供已特殊的 pin 碼，以用於註冊您的智慧卡，使用預設智慧卡 pin 碼值，即 12345678。</span><span class="sxs-lookup"><span data-stu-id="333cb-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="333cb-179">選取 [強制使用者 （您） 若要變更使用智慧卡 PIN 第一次] 選項。</span><span class="sxs-lookup"><span data-stu-id="333cb-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="333cb-180">按一下 **[確定]** 以確認顯示的憑證具備您在其上的資訊。</span><span class="sxs-lookup"><span data-stu-id="333cb-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="333cb-181">一旦您看到已發出憑證的注意事項，請按一下 [**安裝這個憑證**來完成註冊程序。</span><span class="sxs-lookup"><span data-stu-id="333cb-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="333cb-182">使用智慧卡認證登入 Lync</span><span class="sxs-lookup"><span data-stu-id="333cb-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="333cb-183">在第一次使用智慧卡之前，建議您按一下 [**刪除我的登入資訊**Lync 登入頁面。</span><span class="sxs-lookup"><span data-stu-id="333cb-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="333cb-184">執行此動作會清除儲存在您的電腦上任何登入認證，並排除錯誤的可能來源。</span><span class="sxs-lookup"><span data-stu-id="333cb-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="333cb-185">**若要使用智慧卡認證登入 Lync**</span><span class="sxs-lookup"><span data-stu-id="333cb-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="333cb-186">啟動 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="333cb-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="333cb-187">在 [登入畫面，在 [使用者帳戶名稱，在**登入位址**] 方塊中，輸入您的登，然後按一下 [**登入**。</span><span class="sxs-lookup"><span data-stu-id="333cb-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="333cb-188">如果您使用虛擬智慧卡，略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="333cb-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="333cb-189">如果您使用實體智慧卡，插入使用智慧卡到智慧卡讀取和提示若要這麼做，並偵測到卡時，然後按一下 [**確定]** 。</span><span class="sxs-lookup"><span data-stu-id="333cb-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="333cb-190">在中輸入 PIN 碼您智慧卡的然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="333cb-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="333cb-191">如果您不由支援人員指派智慧卡 PIN 碼，使用預設值，即 12345678。</span><span class="sxs-lookup"><span data-stu-id="333cb-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

