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
# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="27ef2-102">在 Microsoft Lync Server 2013 中設定高解析度相片的使用</span><span class="sxs-lookup"><span data-stu-id="27ef2-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27ef2-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="27ef2-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="27ef2-104">Microsoft Lync Server 2010 提供使用者可查看其連絡人之照片的功能 (，並讓其他人) 使用自己的相片。</span><span class="sxs-lookup"><span data-stu-id="27ef2-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="27ef2-105">這些相片通常會儲存為使用者在 Active Directory 中的 thumbnailPhoto 屬性的一部分。</span><span class="sxs-lookup"><span data-stu-id="27ef2-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="27ef2-106">這對相片的大小和解析度造成嚴重限制： thumbnailPhoto 屬性只能保留最大大小為48圖元的相片，48圖元。</span><span class="sxs-lookup"><span data-stu-id="27ef2-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="27ef2-107">不過，Microsoft Lync Server 2013 中的相片可以儲存在使用者的 Microsoft Exchange Server 2013 信箱中;可允許相片大小高達648圖元 x 648 圖元。</span><span class="sxs-lookup"><span data-stu-id="27ef2-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="27ef2-108">除此之外，Exchange 2013 可以根據需要自動調整這些相片的大小，以供不同的產品使用。</span><span class="sxs-lookup"><span data-stu-id="27ef2-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="27ef2-109">通常是指三種不同的相片大小和解析度：</span><span class="sxs-lookup"><span data-stu-id="27ef2-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="27ef2-110">48圖元 x 48 圖元，使用 Active Directory thumbnailPhoto 屬性的大小。</span><span class="sxs-lookup"><span data-stu-id="27ef2-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="27ef2-111">若您將相片上傳至 Exchange 2013 Exchange 會自動建立48圖元乘以該相片的48圖元版本，並更新使用者的 thumbnailPhoto 屬性。</span><span class="sxs-lookup"><span data-stu-id="27ef2-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="27ef2-112">不過，請注意，reverse 不是 true：如果您手動更新 Active Directory 中的 thumbnailPhoto 屬性，使用者的 Exchange 2013 信箱中的相片將不會自動更新。</span><span class="sxs-lookup"><span data-stu-id="27ef2-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="27ef2-113">96圖元 x 96 圖元，以用於 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 和 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="27ef2-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="27ef2-114">在 Lync 2013 和 Microsoft Lync Web App 中使用的648圖元乘以648圖元。</span><span class="sxs-lookup"><span data-stu-id="27ef2-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27ef2-115">如果您有資源，建議您上傳648x648 相片;，可提供任何 Office 2013 應用程式的最大解析度及最佳圖片品質。</span><span class="sxs-lookup"><span data-stu-id="27ef2-115">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="27ef2-116">每個具有648x648 大小的 JPEG 相片和60位的深度，會產生大約 240 kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="27ef2-116">Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="27ef2-117">這表示每4個使用者相片需要大約 1 mb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="27ef2-117">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="27ef2-118">使用 Exchange Web 服務存取的高解析度相片可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。</span><span class="sxs-lookup"><span data-stu-id="27ef2-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="27ef2-119">不過，系統管理員可以使用 Exchange 管理命令介面和一系列 Windows PowerShell 命令，更新任何使用者的相片，如下所示：</span><span class="sxs-lookup"><span data-stu-id="27ef2-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="27ef2-120">上一個範例中的第一個命令使用 Get-Content Cmdlet 讀取 file C： \\ 相片Kenmyer.jpg 的內容 \\ ，並將該資料儲存在名為 $photo 的變數中。</span><span class="sxs-lookup"><span data-stu-id="27ef2-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="27ef2-121">在第二個命令中，Exchange Cmdlet Set-UserPhoto 是用於上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="27ef2-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27ef2-122">在此範例中，Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。</span><span class="sxs-lookup"><span data-stu-id="27ef2-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="27ef2-123">您也可以使用其他識別碼（例如使用者的 SMTP 位址或其使用者主要名稱）來參考使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="27ef2-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="27ef2-124">如需詳細資訊，請參閱 Set-UserPhoto Cmdlet 的檔 <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> 。</span><span class="sxs-lookup"><span data-stu-id="27ef2-124">See the documentation for the Set-UserPhoto cmdlet at <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="27ef2-125">上傳相片不會像指派該相片到 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="27ef2-125">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="27ef2-126">相反地，上載照片只會導致在 [Outlook Web App 選項] 頁面上顯示該相片的預覽。</span><span class="sxs-lookup"><span data-stu-id="27ef2-126">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="27ef2-127">若要將該相片實際指派給使用者帳戶，使用者必須按一下 [選項] 頁面上的 [ **儲存** ]，否則系統管理員必須執行範例中的第三個命令。</span><span class="sxs-lookup"><span data-stu-id="27ef2-127">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="27ef2-128">第三個命令使用 Save 參數將相片指派給 Ken Myer 的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="27ef2-128">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="27ef2-129">若要確認是否已將新的相片指派給使用者帳戶，Ken Myer 可以登入 Lync 2013，選取 [ **選項**]，然後選取 [ **我的圖片**]。</span><span class="sxs-lookup"><span data-stu-id="27ef2-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="27ef2-130">新上傳的相片應顯示為 Ken 的個人照片。</span><span class="sxs-lookup"><span data-stu-id="27ef2-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="27ef2-131">或者，系統管理員可以啟動 Internet Explorer，並流覽至類似下列的 URL，以確認任何使用者的相片。</span><span class="sxs-lookup"><span data-stu-id="27ef2-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="27ef2-132">如果系統管理員可以使用 Internet Explorer 來查看照片，但是使用者無法在 Lync 2013 中查看其照片，這通常表示 Exchange Web 服務或 Exchange 自動探索服務的連線問題。</span><span class="sxs-lookup"><span data-stu-id="27ef2-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="27ef2-133">請注意，您也不需要進行其他設定，即可讓此相片可在 Lync 2013 中使用。</span><span class="sxs-lookup"><span data-stu-id="27ef2-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="27ef2-134">相反地，照片會在上傳後立即可用，而且已執行 Set-UserPhoto Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27ef2-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

