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
ms.openlocfilehash: e817e86d6f05291192593e2345b9e4bc1c0b6db3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517350"
---
# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>在 Microsoft Lync Server 2013 中設定高解析度相片的使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

Microsoft Lync Server 2010 提供使用者可查看其連絡人之照片的功能 (，並讓其他人) 使用自己的相片。 這些相片通常會儲存為使用者在 Active Directory 中的 thumbnailPhoto 屬性的一部分。 這對相片的大小和解析度造成嚴重限制： thumbnailPhoto 屬性只能保留最大大小為48圖元的相片，48圖元。

不過，Microsoft Lync Server 2013 中的相片可以儲存在使用者的 Microsoft Exchange Server 2013 信箱中;可允許相片大小高達648圖元 x 648 圖元。 除此之外，Exchange 2013 可以根據需要自動調整這些相片的大小，以供不同的產品使用。 通常是指三種不同的相片大小和解析度：

  - 48圖元 x 48 圖元，使用 Active Directory thumbnailPhoto 屬性的大小。 若您將相片上傳至 Exchange 2013 Exchange 會自動建立48圖元乘以該相片的48圖元版本，並更新使用者的 thumbnailPhoto 屬性。 不過，請注意，reverse 不是 true：如果您手動更新 Active Directory 中的 thumbnailPhoto 屬性，使用者的 Exchange 2013 信箱中的相片將不會自動更新。

  - 96圖元 x 96 圖元，以用於 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 和 Lync 2013。

  - 在 Lync 2013 和 Microsoft Lync Web App 中使用的648圖元乘以648圖元。

<div>


> [!NOTE]  
> 如果您有資源，建議您上傳648x648 相片;，可提供任何 Office 2013 應用程式的最大解析度及最佳圖片品質。 每個具有648x648 大小的 JPEG 相片和60位的深度，會產生大約 240 kb 的檔案大小。 這表示每4個使用者相片需要大約 1 mb 的磁碟空間。



</div>

使用 Exchange Web 服務存取的高解析度相片可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。 不過，系統管理員可以使用 Exchange 管理命令介面和一系列 Windows PowerShell 命令，更新任何使用者的相片，如下所示：

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

上一個範例中的第一個命令使用 Get-Content Cmdlet 讀取 file C： \\ 相片Kenmyer.jpg 的內容 \\ ，並將該資料儲存在名為 $photo 的變數中。 在第二個命令中，Exchange Cmdlet Set-UserPhoto 是用於上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。

<div>


> [!NOTE]  
> 在此範例中，Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。 您也可以使用其他識別碼（例如使用者的 SMTP 位址或其使用者主要名稱）來參考使用者帳戶。 如需詳細資訊，請參閱 Set-UserPhoto Cmdlet 的檔 <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> 。



</div>

上傳相片不會像指派該相片到 Ken Myer 的使用者帳戶。 相反地，上載照片只會導致在 [Outlook Web App 選項] 頁面上顯示該相片的預覽。 若要將該相片實際指派給使用者帳戶，使用者必須按一下 [選項] 頁面上的 [ **儲存** ]，否則系統管理員必須執行範例中的第三個命令。 第三個命令使用 Save 參數將相片指派給 Ken Myer 的使用者帳戶：

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

若要確認是否已將新的相片指派給使用者帳戶，Ken Myer 可以登入 Lync 2013，選取 [ **選項**]，然後選取 [ **我的圖片**]。 新上傳的相片應顯示為 Ken 的個人照片。 或者，系統管理員可以啟動 Internet Explorer，並流覽至類似下列的 URL，以確認任何使用者的相片。

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

如果系統管理員可以使用 Internet Explorer 來查看照片，但是使用者無法在 Lync 2013 中查看其照片，這通常表示 Exchange Web 服務或 Exchange 自動探索服務的連線問題。

請注意，您也不需要進行其他設定，即可讓此相片可在 Lync 2013 中使用。 相反地，照片會在上傳後立即可用，而且已執行 Set-UserPhoto Cmdlet。

</div>

<span> </span>

</div>

</div>

</div>

