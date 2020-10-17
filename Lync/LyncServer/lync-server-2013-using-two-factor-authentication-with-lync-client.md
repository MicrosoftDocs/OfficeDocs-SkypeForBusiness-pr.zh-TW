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
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>使用 Lync 用戶端和 Lync Server 2013 的雙因素驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-11_

本主題說明如何利用 Lync 2013 用戶端的雙要素驗證。

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>第一次登入 Lync 2013

您的 Lync 登錄資訊通常會在安裝 Lync 2013 時自動設定。 不過，您第一次使用 Lync 時，您可能需要手動啟動用戶端。

**第一次登入 Lync**

1.  登入您組織的網路。

2.  選取 [ **啟動** \> **所有程式**] [ \> **Microsoft Lync \> lync 2013**]。
    
    您應該會看到 [Lync 登錄] 畫面。
    
      - 如果 [登入位址] 方塊已經填入，請確認顯示的位址正確無誤。
    
      - 如果不正確，或如果方塊是空的，請輸入您的 Lync 登入位址 (這通常與您的電子郵件地址) 相同。
    
      - 如果顯示 [空白密碼] 方塊，請新增您的密碼。

3.  選取 [登 **入**]。

</div>

<div>

## <a name="sign-out-of-lync"></a>登出 Lync

當您完成使用 Lync 時，您可以從 [檔案] 功能表中關閉顯示、登出您的會話或從程式退出。 下表說明選項的差異。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>選項</th>
<th>其用途</th>
<th>執行方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>關閉</p></td>
<td><p>關閉您的 Lync 顯示器，但讓識別了您的使用者識別碼的 Lync 會話繼續執行。 如此一來，您就可以繼續取得通知並與其他人互動。</p>
<p>您可以隨時按一下工作列上的 Lync 圖示或螢幕底部的通知區域，以取回顯示。</p></td>
<td><p>在 Lync 主視窗中，執行下列其中一項操作：</p>
<ol>
<li><p>選取 [ <strong>選項</strong> ] 按鈕，然後選取 [ <strong>檔</strong> &gt; <strong>關閉</strong>]。</p></li>
<li><p>按一下視窗右上角 (X) 中的 [ <strong>關閉</strong> ] 按鈕。</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>登出</p></td>
<td><p>結束與您的使用者識別碼相關聯的 Lync 會話，但是 Lync 會繼續在後臺執行。 當您登出時，即會出現登入視窗。</p>
<div>

> [!TIP]  
> 當您登出時，請選取 [ <STRONG>刪除我的登入資訊</STRONG> ]，以移除電腦上的登入識別碼和密碼記錄。 這樣做可能會讓支援人員更容易疑難排解登入問題。 它也可以讓未經授權的使用者難以登入您的認證，以協助確保您的登入資訊更安全。


</div></td>
<td><p>在 Lync 主視窗中，選取 [ <strong>選項</strong> ] 按鈕，然後 <strong>選取 [</strong>檔案] [ &gt; <strong>登出</strong>]。</p></td>
</tr>
<tr class="odd">
<td><p>結束</p></td>
<td><p>結束您的 Lync 會話，並關閉您電腦上的 Lync。 退出後，如果您想要重新開機 Lync，請選取 [ <strong>啟動</strong> &gt; <strong>所有程式</strong>] [ &gt; <strong>Microsoft Lync</strong> &gt; <strong>lync 2013</strong>]。</p></td>
<td><p>在 Lync 主視窗中，選取 [ <strong>選項</strong> ] 按鈕，然後 <strong>選取 [</strong>檔案] [結束] &gt; <strong> </strong>。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>使用智慧卡登入 Lync

有些組織現在會使用多步驟登入處理常式（稱為二要素驗證），以提升其 Lync 2013 使用者的安全性。 如果您想要使用此選項，則需要 "智慧卡" 才能登入 Lync。 智慧卡分為兩種種類、實體和虛擬：

  - **實體**    關於信用卡的大小。 當您登入時，您可以將它插入智慧卡讀取器。

  - **虛擬**    不是實體物件，而是寫入電腦上的特殊晶片的電子識別碼，實際上是在電腦上建立智慧卡。 僅適用于包含 TPM (信任的平臺模組) 晶片的 Windows 8 電腦。

<div>

## <a name="enroll-your-smart-card"></a>註冊您的智慧卡

在您可以使用智慧卡登入時，必須先「登記」智慧卡，也就是您的使用者認證必須透過卡片加以識別。 這種情況是由卡為實體或虛擬的情形所決定。 您的 Lync Server 系統管理員可能已執行此程式。 如果您不確定是否已完成，請與其核對。

<div>


> [!NOTE]  
> 因為每個虛擬智慧卡只會與其安裝裝置相關聯，所以需要為您使用的每一部 Windows 8 電腦登記個別的卡。



</div>

**手動註冊您的智慧卡**

1.  登入您要執行 Lync 的電腦。

2.  使用 Internet Explorer，流覽至組織的 [憑證授權單位網站] [註冊] 頁面。
    
    如果您還沒有這個資源的網址，請詢問您的 Lync Server 管理員。 URL 看起來像這樣： https://MyCA.\ [yourcompanyname \] .com/certsrv。
    
    <div>
    

    > [!NOTE]  
    > 如果您使用的是 Internet Explorer 10，您可能需要在相容性模式中查看此網站。

    
    </div>

3.  當系統提示您登入憑證頁面時，請使用您的網域帳戶登入 (，而不是) 的電腦系統管理員。

4.  在 [網站歡迎] 頁面上，選取 [ **要求憑證**]。

5.  選取 [ **高級要求**]。

6.  選取 [ **建立並提交此 CA 的要求**]，然後按 **[下一步]**。

7.  現在，您會看到一個稱為智慧卡註冊站的頁面。 核准要求以安裝 ActiveX 控制項，然後完成 [高級憑證要求] 表單，如下所示：
    
    1.  從 [**憑證範本**] 下拉式清單中選取 [**智慧卡使用者**]。
    
    2.  選取 [ **建立新的金鑰集**]。
    
    3.  在智慧卡標籤上尋找廠商資訊，然後從 **CSP** 下拉式清單中選取該廠商。
    
    4.  選取 [ **CSP** ] 做為要求格式（如果尚未選取）。
    
    5.  從 [雜湊演算法] 下拉式清單中選取 [ **sha1** ] （如果尚未選取）。
    
    6.  將您要識別的憑證命名為 [名稱]，然後按一下 [ **提交**]。

8.  現在，將空白智慧卡插入附加至註冊站的讀卡機，然後按一下 [ **註冊**]。

9.  出現提示時，請輸入您的個人身分識別號碼 (PIN) ]，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技術支援人員未提供您用來註冊智慧卡的特殊 PIN 碼，請使用預設的智慧卡 PIN 碼值，也就是12345678。

    
    </div>

10. 選取此選項，可強制使用者在第一次使用智慧卡時) 變更 PIN (。

11. 現在，將空白智慧卡插入附加至註冊站的讀卡機，然後按一下 [ **註冊**]。

12. 出現提示時，請輸入您的個人身分識別號碼 (PIN) ]，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的技術支援人員未提供您用來註冊智慧卡的特殊 PIN 碼，請使用預設的智慧卡 PIN 碼值，也就是12345678。

    
    </div>

13. 選取此選項，可強制使用者在第一次使用智慧卡時) 變更 PIN (。

14. 按一下 **[確定]** ，確認顯示的憑證有其資訊。

15. 當您看到已簽發憑證的通知之後，按一下 [ **安裝此憑證** ] 以完成註冊程式。

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>使用智慧卡認證登入 Lync

在您第一次使用智慧卡之前，建議您在 Lync 登入頁面上按一下 [ **刪除我的登入資訊** ]。 這樣做會清除儲存在電腦上的任何登入認證，並消除可能的錯誤來源。

**使用智慧卡認證登入 Lync**

1.  啟動 Lync 用戶端。

2.  在 [登入] 畫面的 [登 **入位址** ] 方塊中，輸入您的登入使用者帳戶名稱，然後按一下 [登 **入**]。

3.  如果您是使用虛擬智慧卡，請略過此步驟。
    
    如果您使用的是實體智慧卡，請將智慧卡插入智慧卡讀取器中，然後提示您執行此動作，然後在偵測到卡時按一下 **[確定]** 。

4.  輸入智慧卡的 PIN 碼號碼，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您的支援人員未指派智慧卡 PIN 碼號碼，請使用預設值，也就是12345678。

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

