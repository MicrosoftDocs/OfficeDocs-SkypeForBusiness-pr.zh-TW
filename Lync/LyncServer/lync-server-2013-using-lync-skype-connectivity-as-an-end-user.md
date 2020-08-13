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

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-27_

Lync-Skype 連線功能可讓 Skype 使用者和 Lync 使用者將彼此新增為連絡人、exchange 立即訊息和進行音訊和視頻通話。 當 Skype 使用者新增 Lync 使用者時，Skype 使用者將在包含會話初始通訊協定 (SIP) 統一資源識別項 (URI) 的 Lync 使用者上建立連絡人。 相反地，當 Lync 使用者新增 Skype 連絡人時，lync 使用者會在 Lync 中建立連絡人，該連絡人會包含 Skype 使用者 (MSA) 中的 Microsoft 帳戶，而不是 Skype 使用者名稱。

**什麼是 MSA？** Skype 使用者必須使用 Microsoft 帳戶登入 Skype (先前稱為 Windows Live ID) ，才能與 Lync 連絡人進行通訊。Microsoft 帳戶包含電子郵件地址和密碼的組合，您也可以用來登入服務，例如 Microsoft OneDrive 儲存技術、Windows Phone、Microsoft Xbox LIVE online 遊戲服務，以及 Microsoft Outlook 郵件和共同作業用戶端 (，但先前是 Microsoft Hotmail web 電子郵件服務或 Windows Live Messenger) 。如果您使用電子郵件地址和密碼來登入這些或其他服務，您已有 Microsoft 帳戶。如需建立 Microsoft 帳戶的詳細資訊，請參閱中的 Microsoft 帳戶註冊頁面 [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) 。 您可以在各種應用程式和服務中，將現有的 Skype 帳戶與 Microsoft 帳戶搭配使用，以進行單一登入。 在合併帳戶後，Skype 使用者可以將連絡人要求傳送至 Lync 使用者。

<div>


> [!IMPORTANT]  
> 為了讓 Lync 和 Skype 使用者完全相互通訊，必須符合下列需求： 
> <UL>
> <LI>
> <P>Skype 使用者必須使用 Microsoft 帳戶登入其 Skype 用戶端 (MSA) 。</P>
> <LI>
> <P>Lync 使用者必須啟用其 Lync 系統管理員的公用 IM 連線。</P>
> <LI>
> <P>當 Skype 使用者新增 Lync 連絡人時，請確認 word Lync 出現在連絡人的名稱下方。 這表示已找到 Lync URI。</P>
> <LI>
> <P>當 Skype 使用者新增 Lync 連絡人，且為該 Lync 網域傳回零搜尋結果時，PIC 布建處理常式可能尚未完成，或 Lync 網域尚未設定。</P>
> <LI>
> <P>根據 Lync 和 Skype 使用者的隱私權設定，IM、影片及顯示狀態可能無法運作，直到每位使用者都接受新的連絡人為止。</P></LI></UL>



</div>

**若要將 Skype 連絡人新增至 Lync 2013**

1.  從 Lync，按一下 [ **新增連絡人]，新增「我的組織」以外的連絡人**。

2.  從可用的連絡人提供者清單中，選取 [ **Skype**]。

3.  在 [ **IM 位址** ] 欄位中，輸入 Microsoft 帳戶 (的 Skype 使用者的 MSA) 。

4.  在 [ **新增至連絡人群組** ] 下拉式方塊中，選取要新增使用者的連絡人群組。

5.  在 [ **設定隱私權關聯** ] 下拉式清單方塊中，選取適當的連絡人設定，然後按一下 **[確定]**。

6.  使用者現在會顯示為 Lync 中的連絡人。 選取使用者，在使用者名稱上按一下滑鼠右鍵，然後按一下 [ **請參閱連絡人卡片** ] 以查看使用者屬性。 您現在可以使用新加入的 Skype 使用者建立音訊或視頻通話。

如需有關連絡人支援的詳細資訊，請參閱 [在 Lync 新增連絡人](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)。

當 Skype 使用者的 Microsoft 帳戶使用自訂的功能變數名稱（例如 <strong>bob@contoso.com</strong> ），lync 使用者可以使用兩種方式將該 Microsoft 帳戶新增至 Lync：

1.  使用 [ **新增連絡人** ] 圖示，或

2.  使用 [ **尋找某人或會議室] 或 [撥打號碼** ] 欄位。

在每個實例中，Lync 使用者必須以下列格式輸入 Skype 使用者的電子郵件： <strong>使用者 (功能變數名稱) @msn .com</strong> 。

<div>


> [!IMPORTANT]  
> 使用下列功能變數名稱的 Microsoft 帳戶，不需要此步驟： <STRONG>@live .com、@hotmail .com 或 @outlook .com</STRONG>。 如需支援的自訂功能變數名稱的詳細資訊，請參閱 <A href="https://support.microsoft.com/kb/897567">支援的公用 IM 網域</A>。



</div>

**使用自訂功能變數名稱將 Skype 連絡人新增至 Lync**

1.  從 Lync，按一下 [ **新增連絡人]，新增「我的組織」以外的連絡人**。

2.  從可用的連絡人提供者清單中，選取 [ **Skype**]。

3.  在 [ **IM 位址** ] 欄位中，以 <strong>使用者 @msn) 名稱 (功能變數名稱</strong> (MSA) ，輸入 Microsoft 帳戶 MSA。 因此，針對使用者 bob@contoso.com，該專案會是 <strong> 小明 (contoso.com) @msn .com <strong> 。

4.  在 [ **新增至連絡人群組** ] 下拉式清單方塊中，選取要新增使用者的連絡人群組。

5.  在 [ **設定隱私權關聯** ] 下拉式清單方塊中，選取適當的連絡人設定，然後按一下 **[確定]**。

6.  Lync 使用者也可以使用 [ **尋找某人或會議室]，或** 在 Lync 中撥打號碼欄位，並新增類似下列 <strong>使用者 (功能變數名稱) @msn .com</strong> 的位址。 所以針對 bob@contoso.com Microsoft 帳戶，此專案會是 <strong>王俊元 (contoso.com) @msn .com</strong> 。

7.  遵循此程式前面的步驟4和5，將連絡人新增至連絡人群組，並選取適當的隱私權關聯。

**若要將 Lync 連絡人新增至 Skype**

1.  登入 Skype。 Skype 使用者必須使用 Microsoft 帳戶登入其 Skype 用戶端 (MSA) 。

2.  選取 [新增連絡人] 圖示。

3.  輸入 Lync 使用者的 SIP URI。 例如，bob@contoso.com。

4.  當 Skype 發現搜尋結果中的相符時，請尋找 Lync 使用者名稱下方的 [ **lync** ] 字樣。 這表示 Skype 成功找到 Lync 用戶端的 SIP URI。 按一下名稱。

5.  在視窗的右上角，按一下 [新增至連絡人]。

6.  新連絡人現在已新增至您的連絡人清單，但您會看到一個問號，而不是其狀態圖示，直到他們接受您的要求為止。 當您的新連絡人接受您的要求時，您將能夠看到他們線上時、發起 IM 交談，以及進行音訊和視頻通話。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 管理員必須設定 Lync 使用者的原則設定，以允許傳入要求。 否則，Lync 使用者將不會收到來自 Skype 使用者的連絡人要求。 根據 Lync 使用者原則設定的設定，加入 Skype 使用者的要求會出現在 Lync 用戶端的 [ <STRONG>新增</STRONG> ] 索引標籤上。若要開始與 Skype 使用者通訊，Lync 使用者必須將 Skype 使用者新增至 [我的最愛] 清單或連絡人清單。 下圖顯示 Lync 用戶端中 [ <STRONG>新增</STRONG> ] 索引標籤的位置。

    
    </div>

Lync 使用者必須設定 Lync 警示，以確保 Lync 使用者傳送的要求出現，而且可由 Lync 使用者探索。 若要設定 Lync 提醒，請完成下列程式。

**設定 Lync 提醒**

1.  在 Lync 用戶端中，按一下 [ **選項** ] 圖示。

2.  選取 [ **警示**]。

3.  在 **[一般提醒**] 底下，選取 [ **當某人將我加入連絡人清單時，請告訴我**]。

4.  在 [ **不使用 Lync 的連絡人**] 底下，選取 [ **允許邀請，但封鎖所有其他通訊**]。

5.  按一下 **[確定** ] 關閉 [選項] 視窗。

</div>

<span> </span>

</div>

</div>

</div>

