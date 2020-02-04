---
title: Lync Server 2013：以使用者身分使用 Lync-Skype 連線
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
ms.openlocfilehash: 5404a42b0d8e2052541ccb9f9178bf33408c2099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>在 Lync Server 2013 中以使用者身分使用 Lync-Skype 連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-27_

Lync-Skype 連線功能可讓 Skype 使用者和 Lync 使用者將對方新增為連絡人、exchange 立即訊息及進行音訊與視頻通話。 當 Skype 使用者新增 Lync 使用者時，Skype 使用者將會在 Skype 中建立一個連絡人，其中包含 Lync 使用者的會話初始通訊協定（SIP）統一資源識別項（URI）。 相反地，當 Lync 使用者新增 Skype 連絡人時，Lync 使用者將在 Lync 中建立一個連絡人，該連絡人將包含 Skype 使用者的 Microsoft 帳戶（MSA），而不是 Skype 使用者名稱。

**什麼是 MSA？** Skype 使用者必須以 Microsoft 帳戶（先前稱為 Windows Live ID）登入 Skype，才能與 Lync 連絡人進行通訊。Microsoft 帳戶是由電子郵件地址和密碼的組合所組成，您也可以用來登入服務，例如 Microsoft OneDrive 儲存技術、Windows Phone、Microsoft Xbox LIVE online 遊戲服務及 Microsoft Outlook 訊息與共同作業用戶端（以及先前的 Microsoft Hotmail web 電子郵件服務或 Windows Live Messenger）。如果您使用電子郵件地址和密碼登入這些或其他服務，表示您已經有 Microsoft 帳戶。如需建立 Microsoft 帳戶的詳細資訊，請參閱中的 Microsoft 帳戶註冊頁面[https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)。 您可以在各種不同的應用程式和服務中，將現有的 Skype 帳戶與您的 Microsoft 帳戶合併，以進行單一登入。 帳戶合併之後，Skype 使用者就可以傳送聯絡人要求給 Lync 使用者。

<div>


> [!IMPORTANT]  
> 為了讓 Lync 與 Skype 使用者彼此完全通訊，必須符合下列需求： 
> <UL>
> <LI>
> <P>Skype 使用者必須以 Microsoft 帳戶（MSA）登入其 Skype 用戶端。</P>
> <LI>
> <P>Lync 使用者必須透過其 Lync 系統管理員啟用公用 IM 連線。</P>
> <LI>
> <P>當 Skype 使用者新增 Lync 連絡人時，請確認 word Lync 出現在連絡人名稱下方。 這表示已找到 Lync URI。</P>
> <LI>
> <P>當 Skype 使用者新增 Lync 連絡人，且針對該 Lync 網域傳回零搜尋結果時，PIC 設定程式可能尚未完成，或者 Lync 網域尚未設定。</P>
> <LI>
> <P>根據 Lync 與 Skype 使用者的隱私權設定，IM、影片和目前狀態可能無法使用，直到每位使用者都接受新的連絡人。</P></LI></UL>



</div>

**若要新增 Skype 連絡人至 Lync 2013**

1.  在 Lync 中，按一下 [**新增連絡人]，新增非組織內部的連絡人**。

2.  從可用的連絡人提供者清單中，選取 [ **Skype**]。

3.  在 [ **IM 位址**] 欄位中，輸入 Skype 使用者的 Microsoft 帳戶（MSA）。

4.  在 [**新增至連絡人群組**] 下拉式方塊中，選取要新增使用者的連絡人群組。

5.  在 [**設定隱私權關係**] 下拉式清單方塊中，選取適當的連絡人設定，然後按一下 **[確定]**。

6.  使用者現在會顯示為 Lync 中的連絡人。 選取使用者，以滑鼠右鍵按一下使用者名稱，然後按一下 [**查看連絡人卡片**] 來查看使用者屬性。 您現在可以使用新新增的 Skype 使用者來建立音訊或視頻通話。

如需連絡人支援的其他相關資訊，請參閱[在 Lync 中新增連絡人](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)。

當 Skype 使用者的 Microsoft 帳戶使用自訂功能變數名稱（例如<strong>bob@contoso.com</strong> ）時，lync 使用者可以用兩種方式將該 Microsoft 帳戶新增到 Lync：

1.  使用 [**新增連絡人**] 圖示，或

2.  使用 [**尋找某人] 或 [會議室]，或 [撥打號碼**] 欄位。

在每個實例中，Lync 使用者必須以下列格式輸入 Skype 使用者的電子郵件： <strong>user （domain name） @msn .com</strong> 。

<div>


> [!IMPORTANT]  
> 對於使用下列功能變數名稱的 Microsoft 帳戶，不需要執行此步驟： <STRONG>@live .com、@hotmail .com 或 @outlook .com</STRONG>。 如需支援的自訂功能變數名稱的詳細資訊，請參閱<A href="https://support.microsoft.com/kb/897567">支援的公用 IM 網域</A>。



</div>

**若要在使用自訂功能變數名稱時新增 Skype 連絡人至 Lync**

1.  在 Lync 中，按一下 [**新增連絡人]，新增非組織內部的連絡人**。

2.  從可用的連絡人提供者清單中，選取 [ **Skype**]。

3.  在 [ **IM 位址**] 欄位中，在 [<strong>使用者格式（網功能變數名稱稱）] @msn .com</strong>] 中輸入 Skype 使用者的 Microsoft 帳戶（MSA）。 所以針對使用者 bob@contoso.com，該專案會是<strong>bob （contoso） @msn .com<strong> 。

4.  在 [**新增至連絡人群組**] 下拉式清單方塊中，選取要新增使用者的連絡人群組。

5.  在 [**設定隱私權關係**] 下拉式清單方塊中，選取適當的連絡人設定，然後按一下 **[確定]**。

6.  Lync 使用者也可以使用 [**尋找某人] 或 [會議室]，或在 Lync 中撥打電話號碼**欄位，並新增類似下列<strong>使用者（網功能變數名稱稱） @msn .com</strong>的位址。 所以針對 bob@contoso.com Microsoft 帳戶，該專案會是<strong>bob （contoso） @msn .com</strong> 。

7.  依照此程式先前的步驟4和5，將連絡人新增至連絡人群組，並選取適當的隱私權關係。

**若要新增 Lync 連絡人至 Skype**

1.  登入 Skype。 Skype 使用者必須以 Microsoft 帳戶（MSA）登入其 Skype 用戶端。

2.  選取 [新增連絡人] 圖示。

3.  輸入 Lync 使用者的 SIP URI。 例如，bob@contoso.com。

4.  當 Skype 在搜尋結果中找到相符專案時，請尋找 Lync 使用者名稱下方的「 **lync** 」字樣。 這表示 Skype 已成功找到 Lync 用戶端的 SIP URI。 按一下名稱。

5.  在視窗右上角，按一下 [新增至連絡人]。

6.  新的連絡人現在已新增至您的連絡人清單，但在接受您的要求之前，您會看到問號，而不是其狀態圖示。 當您的新連絡人接受您的要求之後，您就可以看到他們在線上、啟動 IM 交談，以及進行音訊與視頻通話。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 管理員必須將 Lync 使用者的原則設定設定為允許傳入的要求。 如果不是，Lync 使用者將不會收到來自 Skype 使用者的聯絡人要求。 根據 Lync 使用者原則設定的設定，新增 Skype 使用者的要求會出現在 Lync 用戶端的 [<STRONG>新增</STRONG>] 索引標籤上。若要開始與 Skype 使用者通訊，Lync 使用者必須將 Skype 使用者新增至 [我的最愛] 清單或連絡人清單。 下圖顯示 [Lync 用戶端] 中 [<STRONG>新增</STRONG>] 索引標籤的位置。

    
    </div>

Lync 使用者必須設定 Lync 通知，以確保已從 Skype 使用者傳送的要求出現，且由 Lync 使用者發現。 若要設定 Lync 通知，請完成下列程式。

**若要設定 Lync 通知**

1.  在 Lync 用戶端上，按一下 [**選項**] 圖示。

2.  選取 [**警示**]。

3.  在 **[一般通知**] 底下，選取 [**有人將我加入連絡人清單時通知我**]。

4.  在 [**不使用 Lync 的連絡人**] 底下，選取 [**允許邀請但封鎖所有其他通訊**]。

5.  按一下 **[確定**] 以關閉 [選項] 視窗。

</div>

<span> </span>

</div>

</div>

</div>

