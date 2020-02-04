---
title: Lync Server 2013：設定高解析度相片的使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cb82c047491a43f2a8682d3a6688f67e76af730
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>在 Microsoft Lync Server 2013 中設定高解析度相片的使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

Microsoft Lync Server 2010 提供使用者查看連絡人相片的能力（並讓其他人可以使用自己的相片）。 在 Active Directory 中，這些相片通常會儲存為使用者的 thumbnailPhoto 屬性。 這針對相片的大小與解析度施加了嚴重限制： thumbnailPhoto 屬性只能保留大小48圖元超過48圖元的相片。

不過，在 Microsoft Lync Server 2013 中，相片可以儲存在使用者的 Microsoft Exchange Server 2013 信箱中;該選項可讓相片大小最多648圖元乘648圖元。 此外，Exchange 2013 還能根據需要自動調整這些相片的大小，以供不同的產品使用。 通常這表示三種不同的相片大小與解析度：

  - 48圖元乘48圖元，此為 Active Directory thumbnailPhoto 屬性所使用的大小。 如果您將相片上傳到 Exchange 2013 Exchange 將自動建立一個48圖元（由該相片的48圖元版本），並更新使用者的 thumbnailPhoto 屬性。 但請注意，反之是不成立的：如果您是手動更新 Active Directory 中的 thumbnailPhoto 屬性，則使用者的 Exchange 2013 信箱中的相片將不會自動更新。

  - 96圖元乘96圖元，可用於 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 及 Lync 2013。

  - 在 Lync 2013 和 Microsoft Lync Web App 中使用648圖元乘648圖元。

<div>


> [!NOTE]  
> 如果您有這些資源，建議您上傳648x648 相片;可提供任何 Office 2013 應用程式中的最大解析度和最佳圖片品質。 每個大小648x648 且深度為24位的 JPEG 相片，都會產生大約 240 kb 的檔案大小。 這表示每4個使用者相片都需要大約 1 mb 的磁碟空間。



</div>

使用 Exchange Web 服務存取的高解析度相片，可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。 不過，管理員可以使用 Exchange 管理命令介面和一系列類似下列的 Windows PowerShell 命令來更新任何使用者的相片：

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

前面範例中的第一個命令是使用 [取得內容] Cmdlet 來朗讀檔案 C：\\相片\\Kenmyer 的內容，並將該資料儲存在名為 $photo 的變數中。 在第二個命令中，Exchange Cmdlet UserPhoto 是用來上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。

<div>


> [!NOTE]  
> 在這個範例中，Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。 您也可以使用其他識別碼（例如使用者的 SMTP 位址或其使用者主要名稱）來參考使用者帳戶。 <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A>如需詳細資訊，請參閱 UserPhoto Cmdlet 的相關檔。



</div>

上傳相片並不相當於將該相片指派給 Ken Myer 的使用者帳戶。 相反地，上傳相片只會產生該相片的預覽，以顯示在 Outlook Web App 的 [選項] 頁面上。 若要將該相片實際指派給使用者帳戶，使用者必須在 [選項] 頁面上按一下 [**儲存**]，否則系統管理員必須執行範例中的第三個命令。 第三個命令使用 Save 參數，將相片指派給 Ken Myer 的使用者帳戶：

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

若要確認已將新相片指派給使用者帳戶，Ken Myer 可以登入 Lync 2013，選取 [**選項**]，然後選取 [**我的圖片**]。 新上傳的相片應該顯示為 Ken 個人相片。 或者，管理員可以啟動 Internet Explorer 並流覽至如下所示的 URL，以驗證任何使用者的相片：

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

如果系統管理員可以使用 Internet Explorer 來查看相片，但是使用者無法在 Lync 2013 中查看他或她的相片，這通常表示 Exchange Web 服務或 Exchange 自動探索服務的連線問題。

請注意，您也不需要進行額外的設定，就能讓此相片在 Lync 2013 中提供。 相反地，相片會在上傳後立即可用，且已執行 UserPhoto Cmdlet。

</div>

<span> </span>

</div>

</div>

</div>

