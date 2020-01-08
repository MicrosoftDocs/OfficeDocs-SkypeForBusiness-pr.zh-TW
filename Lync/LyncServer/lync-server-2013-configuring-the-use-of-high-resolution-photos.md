---
title: Lync Server 2013：設定高解析度相片的使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa45f6a7e3f561e56e5563b5024c84bb5731fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="8fb31-102">在 Microsoft Lync Server 2013 中設定高解析度相片的使用</span><span class="sxs-lookup"><span data-stu-id="8fb31-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fb31-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="8fb31-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8fb31-104">Microsoft Lync Server 2010 提供使用者查看連絡人相片的能力（並讓其他人可以使用自己的相片）。</span><span class="sxs-lookup"><span data-stu-id="8fb31-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="8fb31-105">在 Active Directory 中，這些相片通常會儲存為使用者的 thumbnailPhoto 屬性。</span><span class="sxs-lookup"><span data-stu-id="8fb31-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="8fb31-106">這針對相片的大小與解析度施加了嚴重限制： thumbnailPhoto 屬性只能保留大小48圖元超過48圖元的相片。</span><span class="sxs-lookup"><span data-stu-id="8fb31-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="8fb31-107">不過，在 Microsoft Lync Server 2013 中，相片可以儲存在使用者的 Microsoft Exchange Server 2013 信箱中;該選項可讓相片大小最多648圖元乘648圖元。</span><span class="sxs-lookup"><span data-stu-id="8fb31-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="8fb31-108">此外，Exchange 2013 還能根據需要自動調整這些相片的大小，以供不同的產品使用。</span><span class="sxs-lookup"><span data-stu-id="8fb31-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="8fb31-109">通常這表示三種不同的相片大小與解析度：</span><span class="sxs-lookup"><span data-stu-id="8fb31-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="8fb31-110">48圖元乘48圖元，此為 Active Directory thumbnailPhoto 屬性所使用的大小。</span><span class="sxs-lookup"><span data-stu-id="8fb31-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="8fb31-111">如果您將相片上傳到 Exchange 2013 Exchange 將自動建立一個48圖元（由該相片的48圖元版本），並更新使用者的 thumbnailPhoto 屬性。</span><span class="sxs-lookup"><span data-stu-id="8fb31-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="8fb31-112">但請注意，反之是不成立的：如果您是手動更新 Active Directory 中的 thumbnailPhoto 屬性，則使用者的 Exchange 2013 信箱中的相片將不會自動更新。</span><span class="sxs-lookup"><span data-stu-id="8fb31-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="8fb31-113">96圖元乘96圖元，可用於 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App 及 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="8fb31-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="8fb31-114">在 Lync 2013 和 Microsoft Lync Web App 中使用648圖元乘648圖元。</span><span class="sxs-lookup"><span data-stu-id="8fb31-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fb31-115">如果您有這些資源，建議您上傳648x648 相片;可提供任何 Office 2013 應用程式中的最大解析度和最佳圖片品質。</span><span class="sxs-lookup"><span data-stu-id="8fb31-115">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="8fb31-116">每個大小648x648 且深度為24位的 JPEG 相片，都會產生大約 240 kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="8fb31-116">Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="8fb31-117">這表示每4個使用者相片都需要大約 1 mb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="8fb31-117">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="8fb31-118">使用 Exchange Web 服務存取的高解析度相片，可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。</span><span class="sxs-lookup"><span data-stu-id="8fb31-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="8fb31-119">不過，管理員可以使用 Exchange 管理命令介面和一系列類似下列的 Windows PowerShell 命令來更新任何使用者的相片：</span><span class="sxs-lookup"><span data-stu-id="8fb31-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="8fb31-120">前面範例中的第一個命令是使用 [取得內容] Cmdlet 來朗讀檔案 C：\\相片\\Kenmyer 的內容，並將該資料儲存在名為 $photo 的變數中。</span><span class="sxs-lookup"><span data-stu-id="8fb31-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="8fb31-121">在第二個命令中，Exchange Cmdlet UserPhoto 是用來上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8fb31-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fb31-122">在這個範例中，Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。</span><span class="sxs-lookup"><span data-stu-id="8fb31-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="8fb31-123">您也可以使用其他識別碼（例如使用者的 SMTP 位址或其使用者主要名稱）來參考使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8fb31-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="8fb31-124"><A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A>如需詳細資訊，請參閱 UserPhoto Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="8fb31-124">See the documentation for the Set-UserPhoto cmdlet at <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="8fb31-125">上傳相片並不相當於將該相片指派給 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8fb31-125">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="8fb31-126">相反地，上傳相片只會產生該相片的預覽，以顯示在 Outlook Web App 的 [選項] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="8fb31-126">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="8fb31-127">若要將該相片實際指派給使用者帳戶，使用者必須在 [選項] 頁面上按一下 [**儲存**]，否則系統管理員必須執行範例中的第三個命令。</span><span class="sxs-lookup"><span data-stu-id="8fb31-127">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="8fb31-128">第三個命令使用 Save 參數，將相片指派給 Ken Myer 的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="8fb31-128">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="8fb31-129">若要確認已將新相片指派給使用者帳戶，Ken Myer 可以登入 Lync 2013，選取 [**選項**]，然後選取 [**我的圖片**]。</span><span class="sxs-lookup"><span data-stu-id="8fb31-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="8fb31-130">新上傳的相片應該顯示為 Ken 個人相片。</span><span class="sxs-lookup"><span data-stu-id="8fb31-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="8fb31-131">或者，管理員可以啟動 Internet Explorer 並流覽至如下所示的 URL，以驗證任何使用者的相片：</span><span class="sxs-lookup"><span data-stu-id="8fb31-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="8fb31-132">如果系統管理員可以使用 Internet Explorer 來查看相片，但是使用者無法在 Lync 2013 中查看他或她的相片，這通常表示 Exchange Web 服務或 Exchange 自動探索服務的連線問題。</span><span class="sxs-lookup"><span data-stu-id="8fb31-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="8fb31-133">請注意，您也不需要進行額外的設定，就能讓此相片在 Lync 2013 中提供。</span><span class="sxs-lookup"><span data-stu-id="8fb31-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="8fb31-134">相反地，相片會在上傳後立即可用，且已執行 UserPhoto Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8fb31-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

