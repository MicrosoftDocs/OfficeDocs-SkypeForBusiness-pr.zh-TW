---
title: Lync Server 2013：使用 Lync 用戶端的雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>在 Lync 用戶端和 Lync Server 2013 上使用雙因素驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-11_

本主題說明如何利用 Lync 2013 用戶端的雙因素驗證。

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>第一次登入 Lync 2013

您的 Lync 登入資訊通常是在安裝 Lync 2013 時自動設定。 但第一次使用 Lync 時，您可能必須手動啟動用戶端。

**第一次登入 Lync**

1.  登入您組織的網路。

2.  選取 [**開始** \> **所有程式** \> **] \> Microsoft Lync lync 2013**。
    
    您應該會看到 Lync 登入畫面。
    
      - 如果 [登入位址] 方塊已填入，請確認顯示的位址正確無誤。
    
      - 如果不正確或方塊為空白，請輸入您的 Lync 登入位址（這通常與您的電子郵件地址相同）。
    
      - 如果顯示空白密碼方塊，請新增您的密碼。

3.  選取 [登**入**]。

</div>

<div>

## <a name="sign-out-of-lync"></a>登出 Lync

當您使用完 Lync 後，您可以從 [檔案] 功能表關閉 [顯示]、[登出]、[登出] 或 [離開] 程式。 下表說明選項中的差異。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>件</th>
<th>用途</th>
<th>如何執行</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>結轉</p></td>
<td><p>關閉您的 Lync 顯示，但讓使用您的使用者識別碼識別的 Lync 會話繼續執行。 如此一來，您就可以繼續取得通知並與他人互動。</p>
<p>您可以隨時按一下工作列上的 Lync 圖示或畫面底部的通知區域，即可返回顯示畫面。</p></td>
<td><p>在 Lync 主視窗中，執行下列其中一項操作：</p>
<ol>
<li><p>選取 [<strong>選項</strong>] 按鈕，然後<strong>選取</strong> &gt; [檔案<strong>關閉</strong>]。</p></li>
<li><p>按一下視窗右上角的 [<strong>關閉</strong>] 按鈕（X）。</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>登出</p></td>
<td><p>結束與您的使用者識別碼相關聯的 Lync 會話，但是 Lync 會繼續在背景執行。 當您登出時，就會出現 [登入] 視窗。</p>
<div>

> [!TIP]  
> 當您登出時，選取 [<STRONG>刪除我的登入資訊</STRONG>]，即可從電腦中移除登入識別碼與密碼記錄。 如此一來，您就可以更輕鬆地支援人員對登入問題進行疑難排解。 它也可以讓未授權的使用者難以以您的認證登入，協助確保您的登入資訊更加安全。


</div></td>
<td><p>在 Lync 主視窗中，選取 [<strong>選項</strong>] 按鈕，然後<strong>選取</strong> &gt; [<strong>登出</strong>]。</p></td>
</tr>
<tr class="odd">
<td><p>結束</p></td>
<td><p>結束您的 Lync 會話，然後關閉電腦上的 Lync。 退出後，如果您想要重新開機 Lync，請選取 [<strong>開始</strong> &gt; <strong>所有程式</strong> &gt; ] <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>。</p></td>
<td><p>在 Lync 主視窗中，選取 [<strong>選項</strong>] 按鈕，然後<strong>選取</strong> &gt; [檔案結束<strong>]。</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>使用智慧卡登入 Lync

有些組織現在使用多步驟登入程式（稱為雙因素驗證）來加強其 Lync 2013 使用者的安全性。 如果您想要使用這個選項，您需要「智慧卡」才能登入 Lync。 智慧卡分為兩種種類、物理和虛擬：

  - ****    信用卡的實際大小。 您在登入時將它插入智慧卡閱讀程式。

  - **虛擬**   不是實體物件，而是寫入電腦上特殊晶片的電子識別碼，其實質上會將智慧卡建立在您的電腦中。 僅適用于包含 TPM （可信平臺模組）晶片的 Windows 8 電腦。

<div>

## <a name="enroll-your-smart-card"></a>註冊您的智慧卡

在您可以使用智慧卡登入之前，必須先註冊該卡片，亦即，您的使用者認證必須以卡片加以識別。 不論是物理或虛擬卡，都是這種情況。 您的 Lync Server 系統管理員可能已執行此程式。 如果您不確定是否已完成，請與其確認。

<div>


> [!NOTE]  
> 由於每個虛擬智慧卡都只會與它所安裝的裝置相關聯，因此需要針對您使用的每個 Windows 8 電腦註冊一個單獨的卡片。



</div>

**手動註冊您的智慧卡**

1.  登入您要執行 Lync 的電腦。

2.  使用 Internet Explorer，流覽到貴組織的 [憑證授權單位 Web 註冊] 頁面。
    
    如果您還沒有此資源的網址，請向 Lync Server 系統管理員詢問。 URL 看起來會像這樣： https://MyCA.\[yourcompanyname\]/certsrv]。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用的是 Internet Explorer 10，您可能需要以相容模式查看此網站。

    
    </div>

3.  當系統提示您登入 [認證] 頁面時，請使用您的網域帳戶（而不是您電腦的系統管理員）登入。

4.  在 [網站歡迎] 頁面上，選取 [**要求憑證**]。

5.  選取 [**高級要求**]。

6.  選取 [**建立並提交此 CA 的要求**]，然後按 **[下一步]**。

7.  現在，您會看到一個名為「智慧卡註冊站」的頁面。 核准安裝 ActiveX 控制項的要求，然後完成 [高級證書要求] 表單，如下所示：
    
    1.  從 [**憑證範本**] 下拉式清單中選取 [**智慧卡使用者**]。
    
    2.  選取 [**建立新的金鑰集**]。
    
    3.  在智慧卡標籤上尋找製造商資訊，然後從**CSP**下拉式清單中選取該製造商。
    
    4.  選取 [ **CSP** ] 作為 [要求格式] （如果尚未選取的話）。
    
    5.  從 [雜湊演算法] 下拉式清單中選取 [ **sha1** ] （如果尚未選取）。
    
    6.  為您的憑證提供您要辨識的名稱，然後按一下 [**提交**]。

8.  現在，將您的空白智慧卡插入到註冊站所連接的讀卡機中，然後按一下 [**註冊**]。

9.  出現提示時，請輸入您的個人身分識別號碼（PIN），然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技術支援人員未提供您用來註冊智慧卡的特殊 PIN，請使用預設的智慧卡 PIN 值（即12345678）。

    
    </div>

10. 選取選項，強制使用者（您）在第一次使用智慧卡時變更 PIN。

11. 現在，將您的空白智慧卡插入到註冊站所連接的讀卡機中，然後按一下 [**註冊**]。

12. 出現提示時，請輸入您的個人身分識別號碼（PIN），然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技術支援人員未提供您用來註冊智慧卡的特殊 PIN，請使用預設的智慧卡 PIN 值（即12345678）。

    
    </div>

13. 選取選項，強制使用者（您）在第一次使用智慧卡時變更 PIN。

14. 按一下 **[確定]** 以確認顯示的憑證是否包含您的資訊。

15. 當您看到證書已頒發的通知之後，按一下 [**安裝此憑證**] 以完成註冊程式。

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>使用您的智慧卡認證登入 Lync

第一次使用智慧卡前，建議您按一下 Lync 登入頁面上的 [**刪除我的登入資訊**]。 這樣做會清除儲存在您電腦上的任何登入認證，並消除可能的錯誤來源。

**使用您的智慧卡認證登入 Lync**

1.  啟動 Lync 用戶端。

2.  在 [登入] 畫面的 [登**入位址**] 方塊中，輸入您的登入使用者帳戶名稱，然後按一下 [登**入**]。

3.  如果您使用的是虛擬智慧卡，請略過此步驟。
    
    如果您使用的是 [物理智慧卡]，請將智慧卡插入智慧卡讀取器，然後在檢測到卡時，按一下 **[確定]** 。

4.  輸入您智慧卡的 PIN 碼，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您不是由您的支援人員指派智慧卡 PIN 碼，請使用預設值（即12345678）。

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

