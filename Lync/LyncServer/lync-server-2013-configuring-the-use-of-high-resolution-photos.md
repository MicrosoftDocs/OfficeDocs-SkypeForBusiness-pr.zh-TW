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
ms.openlocfilehash: ec832d3795fc1b83c6a838b15c04be9f2e48d6d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="1f43b-102">在 [Microsoft Lync Server 2013 中設定使用高解析度相片</span><span class="sxs-lookup"><span data-stu-id="1f43b-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f43b-103">_**上次修改主題：** 2014年-02-05_</span><span class="sxs-lookup"><span data-stu-id="1f43b-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="1f43b-104">Microsoft Lync Server 2010 提供讓使用者檢視其連絡人的相片 （和要提供給其他人他們自己的相片）。</span><span class="sxs-lookup"><span data-stu-id="1f43b-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="1f43b-105">通常這些相片儲存在 Active Directory 中的使用者的 thumbnailPhoto 屬性的一部分。</span><span class="sxs-lookup"><span data-stu-id="1f43b-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="1f43b-106">放嚴重的限制大小和相片的解決方法： thumbnailPhoto 屬性只可以保留 48 個像素 48 像素為單位的最大的相片。</span><span class="sxs-lookup"><span data-stu-id="1f43b-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="1f43b-107">在 Microsoft Lync Server 2013 中，不過，相片可以儲存在使用者的 Microsoft Exchange Server 2013 信箱;可讓相片大小達 648 像素 x 648 像素為單位。</span><span class="sxs-lookup"><span data-stu-id="1f43b-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="1f43b-108">所，視 Exchange 2013 可以自動調整這些不同的產品中使用的相片。</span><span class="sxs-lookup"><span data-stu-id="1f43b-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="1f43b-109">通常這表示三個不同的相片大小和解決方法：</span><span class="sxs-lookup"><span data-stu-id="1f43b-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="1f43b-110">像素 48 48 像素，用於 Active Directory 的 thumbnailPhoto 屬性的大小。</span><span class="sxs-lookup"><span data-stu-id="1f43b-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="1f43b-111">如果您上傳相片與 Exchange 2013 Exchange 會自動建立該相片 48 個像素版本 48 個像素，並更新使用者的 thumbnailPhoto 屬性。</span><span class="sxs-lookup"><span data-stu-id="1f43b-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="1f43b-112">不過請注意，回復不是，則為 true： 如果您手動更新在 Active Directory 中的 thumbnailPhoto 屬性在使用者的 Exchange 2013 信箱照片將不會自動會更新。</span><span class="sxs-lookup"><span data-stu-id="1f43b-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="1f43b-113">96 像素 x 96 像素，用於 Microsoft Outlook 2013 Web 應用程式、 Microsoft Outlook 2013、 Microsoft Lync Web App 和 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="1f43b-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="1f43b-114">648 像素 x 648 像素，用於 Lync 2013 與 Microsoft Lync Web App 中。</span><span class="sxs-lookup"><span data-stu-id="1f43b-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f43b-115">如果您有個資源，則建議您上傳 648 x 648 相片;所提供的最大解析度和在任何 Office 2013 應用程式的最佳圖片品質。</span><span class="sxs-lookup"><span data-stu-id="1f43b-115">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="1f43b-116">24 位元會導致檔案大小約 240 kb 的深度 648 x 648 大小與每個 JPEG 相片。</span><span class="sxs-lookup"><span data-stu-id="1f43b-116">Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="1f43b-117">這表示您必須針對每個 4 使用者相片約 1 mb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="1f43b-117">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="1f43b-118">高解析度相片，它會存取使用 Exchange Web 服務，可由使用者正在執行 Outlook 2013 Web 應用程式; 上傳只允許使用者更新自己的相片。</span><span class="sxs-lookup"><span data-stu-id="1f43b-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="1f43b-119">不過，系統管理員，可以更新任何使用者相片使用 Exchange 管理命令介面和一系列的 Windows PowerShell 命令與下列類似：</span><span class="sxs-lookup"><span data-stu-id="1f43b-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="1f43b-120">在上述範例中的第一個命令使用 Get-content 指令程式來讀取內容的檔案 c:\\相片\\Kenmyer.jpg 與儲存在變數中的資料名為 $photo。</span><span class="sxs-lookup"><span data-stu-id="1f43b-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="1f43b-121">在第二個命令中，Exchange cmdlet 集 UserPhoto 用來上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f43b-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f43b-122">在這個範例中，Ken Myer 的 Active Directory 顯示名稱作為身分識別的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f43b-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="1f43b-123">您也可以使用其他的識別項，例如使用者的 SMTP 地址或他/她 User Principal Name 參照的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f43b-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="1f43b-124">請參閱設定 UserPhoto 指令程式在文件<A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A>如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="1f43b-124">See the documentation for the Set-UserPhoto cmdlet at <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="1f43b-125">上傳相片不等同於指派給 Ken Myer 的使用者帳戶的相片。</span><span class="sxs-lookup"><span data-stu-id="1f43b-125">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="1f43b-126">相反地上, 傳相片只會導致該相片與顯示在 [Outlook Web App 選項] 頁面上的預覽。</span><span class="sxs-lookup"><span data-stu-id="1f43b-126">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="1f43b-127">實際將該相片指派給使用者帳戶的使用者必須按一下 [**儲存**在 [選項] 頁面上，或系統管理員必須執行在範例中的第三個命令。</span><span class="sxs-lookup"><span data-stu-id="1f43b-127">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="1f43b-128">第三個命令會使用指派給 Ken Myer 的使用者帳戶的相片儲存參數：</span><span class="sxs-lookup"><span data-stu-id="1f43b-128">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="1f43b-129">若要驗證的使用者帳戶，獲指派新的相片，Ken myer 的使用者可以登入 Lync 2013 選取 [**選項**]，然後選取 [**我的圖片**。</span><span class="sxs-lookup"><span data-stu-id="1f43b-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="1f43b-130">新上傳相片應顯示為 Ken 的個人相片。</span><span class="sxs-lookup"><span data-stu-id="1f43b-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="1f43b-131">或者，系統管理員可以驗證任何使用者的相片啟動 Internet Explorer 並瀏覽至的 URL 類似這樣：</span><span class="sxs-lookup"><span data-stu-id="1f43b-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="1f43b-132">如果系統管理員可以檢視使用 Internet Explorer 的相片，但是使用者無法在 Lync 2013 中檢視他/她的相片，這通常表示 Exchange Web 服務或 Exchange 自動探索服務連線問題。</span><span class="sxs-lookup"><span data-stu-id="1f43b-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="1f43b-133">請注意，無需額外設定時須 Lync 2013 中提供這張相片。</span><span class="sxs-lookup"><span data-stu-id="1f43b-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="1f43b-134">相反地，相片會立即供之後已上傳及執行組 UserPhoto 指令程式。</span><span class="sxs-lookup"><span data-stu-id="1f43b-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

