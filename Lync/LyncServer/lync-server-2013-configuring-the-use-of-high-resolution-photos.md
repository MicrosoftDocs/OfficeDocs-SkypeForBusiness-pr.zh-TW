---
title: Lync Server 2013： 設定使用高解析度相片
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
ms.openlocfilehash: 5a49618cd4039163f22d44f358c29a802037b8b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>在 [Microsoft Lync Server 2013 中設定使用高解析度相片

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

Microsoft Lync Server 2010 提供讓使用者檢視其連絡人的相片 （和要提供給其他人他們自己的相片）。 通常這些相片儲存在 Active Directory 中的使用者的 thumbnailPhoto 屬性的一部分。 放嚴重的限制大小和相片的解決方法： thumbnailPhoto 屬性只可以保留 48 個像素 48 像素為單位的最大的相片。

在 Microsoft Lync Server 2013 中，不過，相片可以儲存在使用者的 Microsoft Exchange Server 2013 信箱;可讓相片大小達 648 像素 x 648 像素為單位。 所，視 Exchange 2013 可以自動調整這些不同的產品中使用的相片。 通常這表示三個不同的相片大小和解決方法：

  - 像素 48 48 像素，用於 Active Directory 的 thumbnailPhoto 屬性的大小。 如果您上傳相片與 Exchange 2013 Exchange 會自動建立該相片 48 個像素版本 48 個像素，並更新使用者的 thumbnailPhoto 屬性。 不過請注意，回復不是，則為 true： 如果您手動更新在 Active Directory 中的 thumbnailPhoto 屬性在使用者的 Exchange 2013 信箱照片將不會自動會更新。

  - 96 像素 x 96 像素，用於 Microsoft Outlook 2013 Web 應用程式、 Microsoft Outlook 2013、 Microsoft Lync Web App 和 Lync 2013。

  - 648 像素 x 648 像素，用於 Lync 2013 與 Microsoft Lync Web App 中。

<div>


> [!NOTE]  
> 如果您有個資源，則建議您上傳 648 x 648 相片;所提供的最大解析度和在任何 Office 2013 應用程式的最佳圖片品質。 24 位元會導致檔案大小約 240 kb 的深度 648 x 648 大小與每個 JPEG 相片。 這表示您必須針對每個 4 使用者相片約 1 mb 的磁碟空間。



</div>

高解析度相片，它會存取使用 Exchange Web 服務，可由使用者正在執行 Outlook 2013 Web 應用程式; 上傳只允許使用者更新自己的相片。 不過，系統管理員，可以更新任何使用者相片使用 Exchange 管理命令介面和一系列的 Windows PowerShell 命令與下列類似：

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

在上述範例中的第一個命令使用 Get-content 指令程式來讀取內容的檔案 c:\\相片\\Kenmyer.jpg 與儲存在變數中的資料名為 $photo。 在第二個命令中，Exchange cmdlet 集 UserPhoto 用來上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。

<div>


> [!NOTE]  
> 在這個範例中，Ken Myer 的 Active Directory 顯示名稱作為身分識別的使用者帳戶。 您也可以使用其他的識別項，例如使用者的 SMTP 地址或他/她 User Principal Name 參照的使用者帳戶。 請參閱設定 UserPhoto 指令程式在文件<A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A>如需詳細資訊



</div>

上傳相片不等同於指派給 Ken Myer 的使用者帳戶的相片。 相反地上, 傳相片只會導致該相片與顯示在 [Outlook Web App 選項] 頁面上的預覽。 實際將該相片指派給使用者帳戶的使用者必須按一下 [**儲存**在 [選項] 頁面上，或系統管理員必須執行在範例中的第三個命令。 第三個命令會使用指派給 Ken Myer 的使用者帳戶的相片儲存參數：

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

若要驗證的使用者帳戶，獲指派新的相片，Ken myer 的使用者可以登入 Lync 2013 選取 [**選項**]，然後選取 [**我的圖片**。 新上傳相片應顯示為 Ken 的個人相片。 或者，系統管理員可以驗證任何使用者的相片啟動 Internet Explorer 並瀏覽至的 URL 類似這樣：

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

如果系統管理員可以檢視使用 Internet Explorer 的相片，但是使用者無法在 Lync 2013 中檢視他/她的相片，這通常表示 Exchange Web 服務或 Exchange 自動探索服務連線問題。

請注意，無需額外設定時須 Lync 2013 中提供這張相片。 相反地，相片會立即供之後已上傳及執行組 UserPhoto 指令程式。

</div>

<span> </span>

</div>

</div>

</div>

