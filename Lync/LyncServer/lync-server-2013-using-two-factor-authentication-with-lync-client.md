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

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>使用 Lync 用戶端和 Lync Server 2013 的雙因素驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-11_

本主題說明如何利用與 Lync 2013 用戶端的雙因素驗證。

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>第一次登入 Lync 2013

安裝 Lync 2013 時，通常會自動設定您的 Lync 登入資訊。 但是，第一次您使用 Lync，您可能需要手動啟動用戶端。

**第一次登入 Lync**

1.  登入您的組織網路。

2.  選取 [**開始** \> **所有程式]** \> **Microsoft Lync \> Lync 2013**。
    
    您應該會看到 Lync 登入畫面。
    
      - 如果已填入登入位址] 方塊中，確認顯示的地址正確無誤。
    
      - 如果不正確，或如果方塊為空白，輸入您 Lync 登入地址 （這通常是您的電子郵件地址相同）。
    
      - 如果會顯示空白密碼] 方塊中，新增您的密碼。

3.  選取 [**登入**。

</div>

<div>

## <a name="sign-out-of-lync"></a>登出 Lync

當您完成使用 Lync 時，您可以關閉顯示畫面中，登出您的工作階段，或結束的程式，所有從 [檔案] 功能表。 下表說明選項] 中的差異。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>其用途</th>
<th>若要執行它的方式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>關閉</p></td>
<td><p>會關閉 Lync 顯示，但可讓 Lync 工作階段識別您的使用者識別碼繼續執行。 這是讓您可以繼續取得通知，並與其他人互動。</p>
<p>您可以透過任何時候回顯示按一下工作列上或螢幕底部的 [通知] 區域上的 Lync 圖示。</p></td>
<td><p>在 Lync 主視窗中，執行下列其中一項：</p>
<ol>
<li><p>選取 [<strong>選項</strong>] 按鈕，然後選取 [<strong>檔案</strong> &gt; <strong>關閉</strong>。</p></li>
<li><p>視窗的右上角中，按一下 [<strong>關閉</strong>] 按鈕 (X)。</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>登出</p></td>
<td><p>結束相關聯的使用者 ID，但 Lync Lync 工作階段繼續在背景執行。 當您登出時，會出現登入視窗。</p>
<div>

> [!TIP]  
> 當您登出，才能從電腦移除您的登入識別碼和密碼的記錄，請選取 [<STRONG>刪除我的登入資訊</STRONG>]。 這麼做可能會讓更容易登入問題進行疑難排解的支援人員。 它也可以協助確保您登入資訊是更安全者難以未經授權的使用者使用您的認證登入。


</div></td>
<td><p>在 Lync 主視窗中，選取 [<strong>選項</strong>] 按鈕，然後選取 [<strong>檔案</strong> &gt; <strong>登出</strong>。</p></td>
</tr>
<tr class="odd">
<td><p>結束</p></td>
<td><p>會結束您的 Lync 工作階段，並關閉 Lync，在您的電腦上。 之後結束，如果您想要重新啟動 Lync，選取 [<strong>啟動</strong> &gt; <strong>所有程式]</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>。</p></td>
<td><p>在 Lync 主視窗中，選取 [<strong>選項</strong>] 按鈕，然後選取 [<strong>檔案</strong> &gt; <strong>結束</strong>。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>登入 Lync 與智慧卡

現在，有些組織會使用多個步驟登入程序，稱為雙因素驗證，以增加其 Lync 2013 使用者的安全性。 如果您所預期，請使用此選項，您必須登入 Lync 」 智慧卡 」。 智慧卡會以兩個實體和虛擬的種類：

  - **實體**   有關信用卡的大小。 您將它插入智慧卡讀取時您登入。

  - **虛擬**   實體的物件，但您的電腦，藉以基本上智慧卡插入您的電腦的特殊晶片取得寫入電子識別碼。 僅適用於 Windows 8 電腦內含 TPM （信任的平台模組） 晶片搭配使用。

<div>

## <a name="enroll-your-smart-card"></a>註冊您的智慧卡

您可以使用智慧卡登入前，卡必須 「 註冊 」，也就是必須卡用來識別您的使用者認證。 實體或虛擬智慧卡是否，這會是這種情況。 此程序可能已經已取出您的 Lync Server 系統管理員執行。 如果您不確定是否會有已完成，請檢查與它們。

<div>


> [!NOTE]  
> 因為每個虛擬智慧卡是只與裝置相關聯上安裝，個別的卡片需要您使用每個 Windows 8 電腦上註冊。



</div>

**若要手動註冊您的智慧卡**

1.  您會在執行 Lync 的電腦登入。

2.  使用 Internet Explorer，瀏覽至您的組織憑證授權單位網頁註冊頁面。
    
    如果您還沒有其此資源的網頁地址要求您的 Lync Server 系統管理員。 URL 看起來像這樣： https://MyCA.\[yourcompanyname\].com/certsrv。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用 Internet Explorer 10，您可能需要在相容性模式中檢視此網站。

    
    </div>

3.  當系統提示您登入 [憑證] 頁面上時，記錄上使用您的網域帳戶 （而不是您電腦的系統管理員）。

4.  在網站的歡迎使用] 頁面中，選取 [**要求憑證**]。

5.  選取 [**進階要求**]。

6.  選取 [**建立並送出要求至此 CA**，然後按 [**下一步**。

7.  現在您會看到一個稱為智慧卡註冊站的頁面。 核准要求以安裝 ActiveX 控制項，並再完成其進階憑證要求表單，如下所示：
    
    1.  從 [**憑證範本**] 下拉式清單中選取**智慧卡使用者**。
    
    2.  選取 [**建立新的金鑰組**。
    
    3.  尋找您的智慧卡在標籤上的製造商資訊並從 [ **CSP** ] 下拉式清單中選取該製造商。
    
    4.  選取**雲端解決方案提供者**要求格式，如果尚未選取。
    
    5.  如果尚未選取，請從雜湊演算法] 下拉式清單中，選取**sha1** 。
    
    6.  授與您的憑證會辨識，並按一下 [**送出**的名稱。

8.  現在您空白的智慧卡插入卡片讀者附加至註冊站，然後按一下 [**註冊**。

9.  出現提示時，輸入您的個人識別碼 (PIN)，然後按一下 [**確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技術支援人員不提供已特殊的 pin 碼，以用於註冊您的智慧卡，使用預設智慧卡 pin 碼值，即 12345678。

    
    </div>

10. 選取 [強制使用者 （您） 若要變更使用智慧卡 PIN 第一次] 選項。

11. 現在您空白的智慧卡插入卡片讀者附加至註冊站，然後按一下 [**註冊**。

12. 出現提示時，輸入您的個人識別碼 (PIN)，然後按一下 [**確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技術支援人員不提供已特殊的 pin 碼，以用於註冊您的智慧卡，使用預設智慧卡 pin 碼值，即 12345678。

    
    </div>

13. 選取 [強制使用者 （您） 若要變更使用智慧卡 PIN 第一次] 選項。

14. 按一下 **[確定]** 以確認顯示的憑證具備您在其上的資訊。

15. 一旦您看到已發出憑證的注意事項，請按一下 [**安裝這個憑證**來完成註冊程序。

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>使用智慧卡認證登入 Lync

在第一次使用智慧卡之前，建議您按一下 [**刪除我的登入資訊**Lync 登入頁面。 執行此動作會清除儲存在您的電腦上任何登入認證，並排除錯誤的可能來源。

**若要使用智慧卡認證登入 Lync**

1.  啟動 Lync 用戶端。

2.  在 [登入畫面，在 [使用者帳戶名稱，在**登入位址**] 方塊中，輸入您的登，然後按一下 [**登入**。

3.  如果您使用虛擬智慧卡，略過此步驟。
    
    如果您使用實體智慧卡，插入使用智慧卡到智慧卡讀取和提示若要這麼做，並偵測到卡時，然後按一下 [**確定]** 。

4.  在中輸入 PIN 碼您智慧卡的然後按一下 [**確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您不由支援人員指派智慧卡 PIN 碼，使用預設值，即 12345678。

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

