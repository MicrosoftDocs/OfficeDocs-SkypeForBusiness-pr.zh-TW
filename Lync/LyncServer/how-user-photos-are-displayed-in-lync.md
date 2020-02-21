---
title: 在 Lync 使用者相片的顯示方式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b2c64d0a147457eb50a778d7909b3ccfbf8fecc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="695c8-102">在 Lync 使用者相片的顯示方式</span><span class="sxs-lookup"><span data-stu-id="695c8-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="695c8-103">_**上次修改主題：** 2014年-08-25_</span><span class="sxs-lookup"><span data-stu-id="695c8-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="695c8-104">**摘要：** 在 Lync 用戶端顯示的使用者相片可以使用，例如何時在會議或 IM 交談中的 Lync 功能而有所不同。</span><span class="sxs-lookup"><span data-stu-id="695c8-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="695c8-105">Lync 2010 推出的功能包括與您要顯示給其他 Lync 使用者的 Lync 設定檔相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="695c8-106">您也可以選擇要在 Lync 用戶端中顯示為連絡人的相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="695c8-107">Lync 2013 中支援的高解析度相片的使用者。</span><span class="sxs-lookup"><span data-stu-id="695c8-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="695c8-108">本主題說明如何取得 Lync 用戶端，並會顯示使用者相片，儲存影像、 每個影像來源，限制及如何將使用者相片使用不同的 Lync 服務。</span><span class="sxs-lookup"><span data-stu-id="695c8-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="695c8-109">規劃考量</span><span class="sxs-lookup"><span data-stu-id="695c8-109">Planning considerations</span></span>

<span data-ttu-id="695c8-110">若要實作使用者相片支援規劃時，您應該考慮下列。</span><span class="sxs-lookup"><span data-stu-id="695c8-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="695c8-111">高畫質使用者相片支援需要使用者的信箱會位於 Exchange 2013 和 Lync 使用者帳戶是 Lync 2013 集區中。</span><span class="sxs-lookup"><span data-stu-id="695c8-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="695c8-112">使用 Lync Server 2013 和 Exchange 2013 環境中僅支援高畫質使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="695c8-113">使用信箱位於 Exchange 2010 上的使用者將會一律用於從 AD DS 的**thumbnailPhoto**屬性做為來源其使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="695c8-114">使用者相片儲存為從 AD DS 的**thumbnailPhoto**屬性不會顯示外部 / 同盟連絡人。</span><span class="sxs-lookup"><span data-stu-id="695c8-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="695c8-115">如果使用者連絡人相片儲存在 AD DS 中，所使用之影像檔案是限制為 96 × 96 像素為單位並不超過 100 KB 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="695c8-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="695c8-116">Lync Server 與 Exchange 伺服器之間的連線會遺失，如果從 AD DS 的使用者的低解析度**thumbnailPhoto**就會顯示，並為內部使用者。</span><span class="sxs-lookup"><span data-stu-id="695c8-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="695c8-117">當前發言者沒有啟用的影片時，高解析度的使用者相片會顯示 Lync 2013 會議中。</span><span class="sxs-lookup"><span data-stu-id="695c8-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="695c8-118">此外，將滑鼠移 over 縮圖相片藝廊中會顯示高解析度相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="695c8-119">Lync 2010 中的使用者相片</span><span class="sxs-lookup"><span data-stu-id="695c8-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="695c8-120">在 Lync 2010 用戶端上，您可以選擇從兩個選項來顯示您的設定檔，將相片**預設公司圖片**並**顯示從網址的圖片**。</span><span class="sxs-lookup"><span data-stu-id="695c8-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="695c8-121">預設公司圖片</span><span class="sxs-lookup"><span data-stu-id="695c8-121">Default corporate picture</span></span>

<span data-ttu-id="695c8-122">當您選擇 [**預設公司圖片**] 選項時，Lync 取得從 Active Directory 網域服務顯示為您的相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="695c8-123">使用的影像是指在 Active Directory 網域服務中的**thumbnailPhoto**屬性的值的圖像。</span><span class="sxs-lookup"><span data-stu-id="695c8-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="695c8-124">這是 Exchange 所用來在 Outlook 中顯示圖像的同一個檔案。</span><span class="sxs-lookup"><span data-stu-id="695c8-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="695c8-125">使用影像從 Active Directory 網域服務的考量包括：</span><span class="sxs-lookup"><span data-stu-id="695c8-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="695c8-126">支援最多 96 像素 x 96 像素為單位的尺寸大小的映像。</span><span class="sxs-lookup"><span data-stu-id="695c8-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="695c8-127">影像的檔案大小是限制為 100 KB。</span><span class="sxs-lookup"><span data-stu-id="695c8-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="695c8-128">根據預設，使用者便能夠變更影像用於的**thumbnailPhoto**屬性，但是不會直接透過 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="695c8-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="695c8-129">您可以透過 Active Directory 網域服務來停用此設定。</span><span class="sxs-lookup"><span data-stu-id="695c8-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="695c8-130">即使是同盟的連絡人，儲存在 Active Directory 網域服務中的影像不會顯示您組織外部的連絡人。</span><span class="sxs-lookup"><span data-stu-id="695c8-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="695c8-131">在大型組織中，儲存及擷取大量使用者的影像可能會影響效能與 Active Directory 網域服務資料庫的大小。</span><span class="sxs-lookup"><span data-stu-id="695c8-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="695c8-132">有限的影像大小與檔案大小代表的意義，可以使用僅限低解析度影像。</span><span class="sxs-lookup"><span data-stu-id="695c8-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="695c8-133">使用者如何管理 Active Directory 網域服務中的其使用者相片</span><span class="sxs-lookup"><span data-stu-id="695c8-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="695c8-134">使用者無法變更其 Active Directory 網域服務的設定檔直接透過 Lync 2010 用戶端中使用的影像。</span><span class="sxs-lookup"><span data-stu-id="695c8-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="695c8-135">他們可以使用下列選項之一若要這麼做，如果有：</span><span class="sxs-lookup"><span data-stu-id="695c8-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="695c8-136">**SharePoint Server**   使用者可以上傳相片與 ' 「 我的網站 」 上 SharePoint 伺服器，並接著[設定設定檔同步處理 sharepoint](https://go.microsoft.com/fwlink/p/?linkid=507466)同步處理 Active Directory 網域服務中的**thumbnailPhoto**屬性的相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="695c8-137">**可公開存取的 URL 上儲存的相片**   使用者可以設定指定的影像他們想要使用可公開存取 URL 其使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="695c8-138">影像必須是不需要密碼可公開存取。</span><span class="sxs-lookup"><span data-stu-id="695c8-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="695c8-139">儲存在指定的網址的影像會被轉接至其他使用者透過 [連絡人卡片] 類別中的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="695c8-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="695c8-140">當 Lync 用戶端需要顯示使用者相片時，它會從指定的網頁地址擷取映像。</span><span class="sxs-lookup"><span data-stu-id="695c8-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="695c8-141">**Windows powershell 的 Exchange 2010 cmdlet**   系統管理員可以管理的**thumbnailPhoto**屬性中的 Exchange 2010 管理命令介面中執行[Import-recipientdataproperty](https://go.microsoft.com/fwlink/p/?linkid=507468)指令程式。</span><span class="sxs-lookup"><span data-stu-id="695c8-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="695c8-142">當影像匯入與 Exchange 2010 cmdlet 的檔案大小是限制為 10 KB。</span><span class="sxs-lookup"><span data-stu-id="695c8-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="695c8-143">**協力廠商工具**   使用者可以上傳僅限自己相片與**thumbnailPhoto**屬性。</span><span class="sxs-lookup"><span data-stu-id="695c8-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="695c8-144">顯示來自網址的圖片</span><span class="sxs-lookup"><span data-stu-id="695c8-144">Show a picture from a web address</span></span>

<span data-ttu-id="695c8-145">當您選擇 [**顯示來自網址的圖片**] 選項時，Lync 會取得圖像處輸入，並將其顯示為您的使用者相片 Lync 中的地址。</span><span class="sxs-lookup"><span data-stu-id="695c8-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="695c8-146">下面是使用影像網頁的地址的注意事項：</span><span class="sxs-lookup"><span data-stu-id="695c8-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="695c8-147">檔案大小限制會取決於**MaxPhotoSizeKB**屬性在用戶端原則中，使用[New-csclientpolicy](https://go.microsoft.com/fwlink/p/?linkid=507463)指令程式來定義。</span><span class="sxs-lookup"><span data-stu-id="695c8-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="695c8-148">預設的大小限制為 30 KB。</span><span class="sxs-lookup"><span data-stu-id="695c8-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="695c8-149">最大值為 100 KB。</span><span class="sxs-lookup"><span data-stu-id="695c8-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="695c8-150">在此映像的解析度沒有限制，但如果您嘗試使用映像檔超過大小限制，它將不會下載到 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="695c8-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="695c8-151">您可以設定此值為 0，即可停用 Lync 中使用的所有使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="695c8-152">外部同盟連絡人可以看到從網址的使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="695c8-153">管理使用者的相片與用戶端原則指令程式</span><span class="sxs-lookup"><span data-stu-id="695c8-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="695c8-154">在 Lync Server 2010 中，用戶端原則設定來設定 CsClientPolicy 指令程式。</span><span class="sxs-lookup"><span data-stu-id="695c8-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="695c8-155">設定的原則設定會傳送至用戶端透過頻內佈建。</span><span class="sxs-lookup"><span data-stu-id="695c8-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="695c8-156">決定使用者相片體驗 CsClientPolicy cmdlet 的兩個參數，而**DisplayPhoto** **MaxPhotoSizeKB**。</span><span class="sxs-lookup"><span data-stu-id="695c8-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="695c8-157">**DisplayPhoto**和**MaxPhotoSizeKB**對應的頻內佈建參數是名為**PhotoUsage**。</span><span class="sxs-lookup"><span data-stu-id="695c8-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="695c8-158">**PhotoUsage**參數的值是透過**endpointConfiguration** **provisionGroup**的用戶端傳送。</span><span class="sxs-lookup"><span data-stu-id="695c8-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="695c8-159">如需詳細資訊，請參閱[概觀的用戶端原則和設定](https://go.microsoft.com/fwlink/?linkid=507470)。</span><span class="sxs-lookup"><span data-stu-id="695c8-159">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="695c8-160">**DisplayPhoto**參數值會決定使用者的相片影像的來源。</span><span class="sxs-lookup"><span data-stu-id="695c8-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="695c8-161">下列資料表中所含之支援的值。</span><span class="sxs-lookup"><span data-stu-id="695c8-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="695c8-162">DisplayPhoto 參數值</span><span class="sxs-lookup"><span data-stu-id="695c8-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="695c8-163">影像來源</span><span class="sxs-lookup"><span data-stu-id="695c8-163">Image source</span></span></th>
<th><span data-ttu-id="695c8-164">Lync 2010 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="695c8-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="695c8-165">Nophoto:</span><span class="sxs-lookup"><span data-stu-id="695c8-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="695c8-166">無</span><span class="sxs-lookup"><span data-stu-id="695c8-166">none</span></span></p></td>
<td><p><span data-ttu-id="695c8-167"><strong>不顯示我的圖片</strong></span><span class="sxs-lookup"><span data-stu-id="695c8-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="695c8-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="695c8-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="695c8-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="695c8-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="695c8-170"><strong>預設公司圖片</strong></span><span class="sxs-lookup"><span data-stu-id="695c8-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="695c8-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="695c8-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="695c8-172">網址</span><span class="sxs-lookup"><span data-stu-id="695c8-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="695c8-173"><strong>顯示來自網址的圖片</strong></span><span class="sxs-lookup"><span data-stu-id="695c8-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="695c8-174">Lync 2010 用戶端如何取得相片</span><span class="sxs-lookup"><span data-stu-id="695c8-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="695c8-175">在 Lync 2010 中，使用者相片會在伺服器上管理通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="695c8-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="695c8-176">Lync 用戶端第一個查詢公開透過通訊群組清單擴充 web 服務的伺服器上的地址通訊錄 Web 查詢 (ABWQ) 服務來取得使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="695c8-177">用戶端接收的影像檔，並再將它複製到使用者的快取，以避免下載映像需要顯示每次。</span><span class="sxs-lookup"><span data-stu-id="695c8-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="695c8-178">從查詢傳回的屬性值也會儲存在使用者的快取通訊錄服務項目。</span><span class="sxs-lookup"><span data-stu-id="695c8-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="695c8-179">通訊錄服務會刪除所有快取的影像每隔 24 小時，這表示，可能需要 24 小時的時間進行更新的新使用者影像的伺服器上快取中。</span><span class="sxs-lookup"><span data-stu-id="695c8-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="695c8-180">您可以使用[Update-csaddressbook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet 強制執行更新快取。</span><span class="sxs-lookup"><span data-stu-id="695c8-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="695c8-181">包含在目前狀態的使用者相片也具有 Lync 用戶端用來判斷是否有可用的較新的圖像相關聯的雜湊值。</span><span class="sxs-lookup"><span data-stu-id="695c8-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="695c8-182">用戶端會自動收到的使用中的目前狀態的影像檔案的變更通知。</span><span class="sxs-lookup"><span data-stu-id="695c8-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="695c8-183">因為相片不會儲存在 GalContacts.db 資料庫中，下載使用者相片不是取決於用戶端原則 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-csclientpolicy</A>) 中 [ <STRONG>AddressBookAvailability</STRONG>設定。</span><span class="sxs-lookup"><span data-stu-id="695c8-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="695c8-184">ABWQ 服務查詢包含下列屬性：</span><span class="sxs-lookup"><span data-stu-id="695c8-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="695c8-185">**PhotoHash**   雜湊資料的值二進位相片，而且會用來判斷是否已變更目前的相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="695c8-186">**PhotoRelPath**   影像檔案儲存在伺服器上的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="695c8-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="695c8-187">**PhotoSize**   影像檔，以位元組為單位的大小。</span><span class="sxs-lookup"><span data-stu-id="695c8-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="695c8-188">**時間戳記**   的日期和時間的影像檔上次從伺服器下載並複製到用戶端快取。</span><span class="sxs-lookup"><span data-stu-id="695c8-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="695c8-189">接下來之後擷取映像檔，Lync 2010 用戶端比較，看看它們是否不同用戶端從頻內佈建接收到的屬性值對查詢所傳回的屬性值。</span><span class="sxs-lookup"><span data-stu-id="695c8-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="695c8-190">如果值不同，用戶端會擷取 HTTP GET 要求的登入使用者的圖像檔案。</span><span class="sxs-lookup"><span data-stu-id="695c8-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="695c8-191">此外，用戶端檢查與伺服器進行比較的值在用戶端上的伺服器上**PhotoHash**屬性的值建立影像檔案的快取的版本的速率時間從每隔 24 小時。</span><span class="sxs-lookup"><span data-stu-id="695c8-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="695c8-192">如果值不同，用戶端會知道已變更，圖像檔案。</span><span class="sxs-lookup"><span data-stu-id="695c8-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="695c8-193">若要取得更新的影像檔案，用戶端重新查詢 ABWQ 要更新的服務用戶端快取中的影像檔與影像檔案在伺服器上，這也會重設**的時間戳記**的用戶端快取中的檔案。</span><span class="sxs-lookup"><span data-stu-id="695c8-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="695c8-194">以下是將查詢傳送至 ABWQ 服務範例回應：</span><span class="sxs-lookup"><span data-stu-id="695c8-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="695c8-195">Lync 2013 中的使用者相片</span><span class="sxs-lookup"><span data-stu-id="695c8-195">User photos in Lync 2013</span></span>

<span data-ttu-id="695c8-196">Lync 2013 引進了使用者相片高解析度影像的支援。</span><span class="sxs-lookup"><span data-stu-id="695c8-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="695c8-197">Lync 2013 還包含支援將使用者相片儲存在使用者的信箱在 Exchange 2013 中，會移除映像的解析度和 Lync 2010 中呈現的大小限制。</span><span class="sxs-lookup"><span data-stu-id="695c8-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="695c8-198">Lync 2013 中的使用者相片可以最多 648 像素 x 648 像素，最多 20 MB 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="695c8-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="695c8-199">在 Lync 2013 的高解析度相片必須位於 Exchange 2013 中，使用者的信箱，並只支援 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="695c8-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="695c8-200">這與 Exchange 整合善用 Lync、 Exchange 和稱為 Oauth 的 SharePoint 2013 版本中包含的新授權架構。</span><span class="sxs-lookup"><span data-stu-id="695c8-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="695c8-201">如果 Exchange 2013 不適用於您的部署，支援的使用者相片與 Lync 2010 相同。</span><span class="sxs-lookup"><span data-stu-id="695c8-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="695c8-202">不過，若要選擇使用相片使用者選項各有不同 Lync 2013 用戶端中。</span><span class="sxs-lookup"><span data-stu-id="695c8-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="695c8-203">在 Lync 2013 用戶端，使用者可以選取 [**隱藏我的圖片**] 或 [**顯示我的圖片**。</span><span class="sxs-lookup"><span data-stu-id="695c8-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="695c8-204">**顯示網站中的圖片**] 選項不是依預設，可使用，但可以藉由將用戶端原則指派啟用。</span><span class="sxs-lookup"><span data-stu-id="695c8-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="695c8-205">隱藏我的圖片</span><span class="sxs-lookup"><span data-stu-id="695c8-205">Hide my picture</span></span>

<span data-ttu-id="695c8-206">使用者相片設定不在 Lync 2013 中的 [**選項**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="695c8-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="695c8-207">當您選擇**隱藏我的圖片**時，沒有使用者相片會顯示為您在 Lync 用戶端，但在您的連絡人卡片上及 Lync 外，仍顯示相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="695c8-208">顯示我的圖片</span><span class="sxs-lookup"><span data-stu-id="695c8-208">Show my picture</span></span>

<span data-ttu-id="695c8-209">當您選擇 [**顯示我的圖片**] 選項時，您的使用者相片會顯示在您的 Lync 用戶端，並將 Lync 交談中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="695c8-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="695c8-210">使用的影像是儲存在 AD DS。</span><span class="sxs-lookup"><span data-stu-id="695c8-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="695c8-211">顯示網站中的圖片</span><span class="sxs-lookup"><span data-stu-id="695c8-211">Show a picture from a website</span></span>

<span data-ttu-id="695c8-212">**顯示從網站的圖片**] 選項可在 Lync 2013 後的用戶端原則設為啟用它。</span><span class="sxs-lookup"><span data-stu-id="695c8-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="695c8-213">用戶端版本必須比 15.0.4535.1002，則會以安裝更新[Lync 累計更新： 11 月 2013年](https://go.microsoft.com/fwlink/p/?linkid=509908)。</span><span class="sxs-lookup"><span data-stu-id="695c8-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="695c8-214">使用者可能需要登出，然後再重新中若要查看在用戶端的變更。</span><span class="sxs-lookup"><span data-stu-id="695c8-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="695c8-215">您可以設定用戶端原則，以便**顯示從網站的圖片**設定 Lync Server 管理命令介面中執行的[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)原則。</span><span class="sxs-lookup"><span data-stu-id="695c8-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="695c8-216">下列範例指令程式會示範如何部署中的所有使用者的全域設定的原則：</span><span class="sxs-lookup"><span data-stu-id="695c8-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="695c8-217">當影像上傳到使用者的信箱時，Exchange 會自動建立的影像，可以使用的低解析度版本用戶端應用程式中。</span><span class="sxs-lookup"><span data-stu-id="695c8-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="695c8-218">使用者相片也會更新 AD DS 中。</span><span class="sxs-lookup"><span data-stu-id="695c8-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="695c8-219">當影像檔案更新 AD DS 中時，48 x 48 像素影像建立，並使用 AD DS 中 thumbnailPhoto。</span><span class="sxs-lookup"><span data-stu-id="695c8-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="695c8-220">會取代任何現有的影像。</span><span class="sxs-lookup"><span data-stu-id="695c8-220">Any existing image is replaced.</span></span> <span data-ttu-id="695c8-221">因此如果您已為 96 x 96 影像新增至 AD DS，它會覆寫新 48 x 48 圖像。</span><span class="sxs-lookup"><span data-stu-id="695c8-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="695c8-222">這是只有重要是您使用 Lync 2010 用戶端，您環境中有使用者，因為這些用戶端會從 AD DS 取得使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="695c8-223">您可以匯入來取代有 Lync 2010 用戶端在組織中建立的 AD DS 的那些 96 x 96 像素影像。</span><span class="sxs-lookup"><span data-stu-id="695c8-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="695c8-224">Lync 2013 中的使用者相片支援</span><span class="sxs-lookup"><span data-stu-id="695c8-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="695c8-225">在 Lync 2013 中，三個圖像解析度支援使用者相片，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="695c8-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="695c8-226">使用影像取決於指派給 Lync 使用者的用戶端原則設定。</span><span class="sxs-lookup"><span data-stu-id="695c8-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="695c8-227">「 管理使用者的相片與用戶端原則指令程式搭配 「 在此主題以取得詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="695c8-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="695c8-228">影像解析度 （像素為單位）</span><span class="sxs-lookup"><span data-stu-id="695c8-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="695c8-229">應用程式</span><span class="sxs-lookup"><span data-stu-id="695c8-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="695c8-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="695c8-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="695c8-231">如果已選取 [沒有高解析度影像</span><span class="sxs-lookup"><span data-stu-id="695c8-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="695c8-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="695c8-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="695c8-233">Outlook Web App 和 Outlook 2013 中使用</span><span class="sxs-lookup"><span data-stu-id="695c8-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="695c8-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="695c8-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="695c8-235">Lync 2013 桌面用戶端和 Lync 2013 Web 應用程式中使用</span><span class="sxs-lookup"><span data-stu-id="695c8-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="695c8-236">任何具有 Exchange 2013 中啟用信箱的使用者可以上傳不同的映像，包括高解析度相片，透過 Outlook Web Access 或 Lync 2013 用戶端選項。</span><span class="sxs-lookup"><span data-stu-id="695c8-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="695c8-237">所用的圖像的建議的設定包括：</span><span class="sxs-lookup"><span data-stu-id="695c8-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="695c8-238">**影像解析度**   648 由 648 像素為單位</span><span class="sxs-lookup"><span data-stu-id="695c8-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="695c8-239">**色彩深度**   24 位元</span><span class="sxs-lookup"><span data-stu-id="695c8-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="695c8-240">**影像檔案大小**   設為 20 MB</span><span class="sxs-lookup"><span data-stu-id="695c8-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="695c8-241">**檔案格式**   JPEG</span><span class="sxs-lookup"><span data-stu-id="695c8-241">**File format**   JPEG</span></span>

<span data-ttu-id="695c8-242">為 648 像素 x 648 像素為單位的一般 24 位元 JPEG 圖像有檔案大小約為 240 kb，所以 1 MB 的儲存空間所需的每個 4 使用者相片。</span><span class="sxs-lookup"><span data-stu-id="695c8-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

