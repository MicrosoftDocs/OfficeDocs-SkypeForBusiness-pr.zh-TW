---
title: Lync 中使用者相片的顯示方式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac13f066c24f66640aee1360caf1d341d604474
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40981730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="8f6c2-102">Lync 中使用者相片的顯示方式</span><span class="sxs-lookup"><span data-stu-id="8f6c2-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f6c2-103">_**主題上次修改日期：** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="8f6c2-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="8f6c2-104">**摘要：** 根據您所使用的 Lync 功能（例如在會議或 IM 聊天中時），在 Lync 用戶端上顯示的使用者相片可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="8f6c2-105">Lync 2010 引進了將相片與您的 Lync 設定檔一起提供給其他 Lync 使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="8f6c2-106">您也可以選擇是否要在 Lync 用戶端中顯示連絡人的相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="8f6c2-107">在 Lync 2013 中，為使用者提供高解析度相片的支援。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="8f6c2-108">本主題說明 Lync 用戶端如何取得及顯示使用者相片、儲存影像的位置、每個影像來源的限制，以及使用者相片如何由不同的 Lync 服務使用。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="8f6c2-109">規劃考慮</span><span class="sxs-lookup"><span data-stu-id="8f6c2-109">Planning considerations</span></span>

<span data-ttu-id="8f6c2-110">規劃執行使用者相片支援時，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="8f6c2-111">高定義使用者相片支援要求使用者的信箱位於 Exchange 2013，而 Lync 使用者帳戶位於 Lync 2013 池中。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="8f6c2-112">只有在使用 Lync Server 2013 與 Exchange 2013 的環境中，才能支援高定義使用者相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="8f6c2-113">在 Exchange 2010 上擁有信箱的使用者，將永遠會使用**thumbnailPhoto**屬性（從 AD DS 做為其使用者相片的來源）。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="8f6c2-114">從 AD DS 儲存為**thumbnailPhoto**屬性的使用者相片，不會顯示在外部/同盟連絡人。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="8f6c2-115">如果使用者連絡人的相片儲存在 AD DS 中，則所使用的圖像檔案將限制為96×96圖元且不超過 100 KB 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="8f6c2-116">如果 Lync Server 與 Exchange Server 之間的連線能力遺失，就會顯示使用者的來自 AD DS 的低解析度**thumbnailPhoto** ，且僅供內部使用者使用。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="8f6c2-117">當使用中的喇叭沒有啟用影片時，會在 Lync 2013 會議中顯示高解析度的使用者相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="8f6c2-118">此外，將滑鼠移到圖庫中的縮圖相片上方，就會顯示高解析度相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="8f6c2-119">Lync 2010 中的使用者相片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="8f6c2-120">在 Lync 2010 用戶端中，您可以選擇兩種選項來顯示設定檔的相片、**預設的 [公司圖片**]，以及 [**從網址顯示圖片**]。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="8f6c2-121">預設的公司圖片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-121">Default corporate picture</span></span>

<span data-ttu-id="8f6c2-122">當您選擇 [**預設的公司圖片**] 選項時，Lync 會從 Active Directory 網域服務取得為您顯示的相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="8f6c2-123">所使用的影像是在 Active Directory 網域服務中定義為**thumbnailPhoto**屬性值的影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="8f6c2-124">這是 Exchange 在 Outlook 中顯示影像時所使用的相同檔案。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="8f6c2-125">使用 Active Directory 網域服務中的影像時的考慮事項如下：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="8f6c2-126">僅支援最大為96圖元乘96圖元的影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="8f6c2-127">影像的檔案大小限制為 100 KB。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="8f6c2-128">根據預設，使用者可以變更**thumbnailPhoto**屬性所使用的影像，但不直接透過 Lync 用戶端進行。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="8f6c2-129">您可以透過 Active Directory 網域服務停用此狀態。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="8f6c2-130">儲存在 Active Directory 網域服務中的圖像，不會顯示給您組織外部的連絡人，即使他們是同盟連絡人也一樣。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="8f6c2-131">在大型組織中，針對大量使用者儲存及檢索影像，可能會影響 Active Directory 網域服務資料庫的大小和效能。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="8f6c2-132">受限制的圖像尺寸與檔案大小代表只有低解析度影像可供使用。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="8f6c2-133">使用者如何在 Active Directory 網域服務中管理使用者的相片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="8f6c2-134">使用者無法透過 Lync 2010 用戶端直接變更 Active Directory 網域服務設定檔中所使用的影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="8f6c2-135">如果有的話，他們可以使用下列其中一個選項來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="8f6c2-136">**Sharepoint server**   使用者可以在 sharepoint 伺服器上將相片上傳到「我的網站」，然後[設定 sharepoint 中的設定檔同步](http://go.microsoft.com/fwlink/p/?linkid=507466)處理，將相片同步處理到 Active Directory 網域服務中的**thumbnailPhoto**屬性。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="8f6c2-137">**儲存在可公開存取的 URL**   的相片，使用者可以設定其使用者相片，指定要使用之影像的公開存取 url。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="8f6c2-138">在沒有密碼的情況下，影像必須能夠公開存取。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="8f6c2-139">儲存在指定網址的影像會透過目前狀態資訊的連絡人卡片類別傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="8f6c2-140">當 Lync 用戶端需要顯示使用者相片時，它會從指定的網址中檢索影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="8f6c2-141">**Windows PowerShell**   系統管理員的 exchange 2010 Cmdlet 可以在 exchange 2010 管理 Shell 中執行[RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) Cmdlet，以管理**thumbnailPhoto**屬性。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="8f6c2-142">在使用 Exchange 2010 Cmdlet 匯入影像時，檔案大小限制為 10 KB。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="8f6c2-143">**協力廠商工具**   使用者只能將自己的相片上傳給**thumbnailPhoto**屬性。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="8f6c2-144">從網址顯示圖片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-144">Show a picture from a web address</span></span>

<span data-ttu-id="8f6c2-145">當您選擇 [**從網址顯示圖片**] 選項時，Lync 會在您輸入的位址中取得圖像，並在 Lync 中針對您的使用者相片顯示該影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="8f6c2-146">使用網址中的圖像的考慮事項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="8f6c2-147">檔案大小限制是由用戶端原則中使用[CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) Cmdlet 定義的**MaxPhotoSizeKB**屬性所決定。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="8f6c2-148">預設大小限制為 30 KB。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="8f6c2-149">最大值為 100 KB。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="8f6c2-150">圖像的解析度沒有限制，但如果您嘗試使用超過大小限制的圖像檔案，則不會將其下載至 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="8f6c2-151">您可以將此值設定為0，以停用 Lync 中的所有使用者相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="8f6c2-152">外部同盟連絡人可以看到來自網址的使用者相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="8f6c2-153">使用用戶端原則 Cmdlet 管理使用者的相片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="8f6c2-154">在 Lync Server 2010 中，用戶端原則設定是使用 CsClientPolicy Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="8f6c2-155">設定的原則設定會透過頻帶內設定傳送至用戶端。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="8f6c2-156">判斷使用者相片體驗的 CsClientPolicy Cmdlet 的兩個參數是**DisplayPhoto**和**MaxPhotoSizeKB**。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="8f6c2-157">**DisplayPhoto**和**MaxPhotoSizeKB**的對應內建提供參數已命名為**PhotoUsage**。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="8f6c2-158">**PhotoUsage**參數的值會透過**endpointConfiguration** **provisionGroup**傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="8f6c2-159">如需詳細資訊，請參閱[用戶端原則與設定的概覽](http://go.microsoft.com/fwlink/?linkid=507470)。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-159">See [Overview of Client Policies and Settings](http://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="8f6c2-160">**DisplayPhoto**參數值決定使用者相片影像的來源。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="8f6c2-161">下表包含支援的值。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f6c2-162">DisplayPhoto 參數值</span><span class="sxs-lookup"><span data-stu-id="8f6c2-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="8f6c2-163">影像來源</span><span class="sxs-lookup"><span data-stu-id="8f6c2-163">Image source</span></span></th>
<th><span data-ttu-id="8f6c2-164">Lync 2010 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="8f6c2-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f6c2-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="8f6c2-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-166">所有</span><span class="sxs-lookup"><span data-stu-id="8f6c2-166">none</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-167"><strong>不要顯示我的圖片</strong></span><span class="sxs-lookup"><span data-stu-id="8f6c2-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f6c2-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="8f6c2-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="8f6c2-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-170"><strong>預設的公司圖片</strong></span><span class="sxs-lookup"><span data-stu-id="8f6c2-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f6c2-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="8f6c2-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-172">網址</span><span class="sxs-lookup"><span data-stu-id="8f6c2-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-173"><strong>從網址顯示圖片</strong></span><span class="sxs-lookup"><span data-stu-id="8f6c2-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="8f6c2-174">Lync 2010 用戶端如何取得相片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="8f6c2-175">在 Lync 2010 中，使用者相片是透過通訊錄服務在伺服器上管理。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="8f6c2-176">Lync 用戶端會先查詢伺服器上的通訊錄網頁查詢（ABWQ）服務（透過通訊組展開 Web 服務公開），以取得使用者相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="8f6c2-177">用戶端會收到映射檔，然後將它複製到使用者的快取，以避免在每次需要顯示圖像時下載影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="8f6c2-178">從查詢傳回的屬性值也會儲存在使用者的快取通訊錄服務專案中。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="8f6c2-179">通訊錄服務每24小時都會刪除所有快取的影像，這表示在伺服器上的快取中，新的使用者影像可能需要長達24小時才能更新。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="8f6c2-180">您可以使用[CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) Cmdlet 強制更新快取。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="8f6c2-181">目前狀態中包含的使用者相片也有一個相關聯的雜湊值，由 Lync 用戶端用來判斷是否有可用的較新影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="8f6c2-182">用戶端會在目前狀態中使用的影像檔案自動收到變更通知。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="8f6c2-183">因為相片未儲存在 GalContacts 資料庫中，所以下載使用者相片並不依賴于用戶端原則中的<STRONG>AddressBookAvailability</STRONG>設定（<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>）。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="8f6c2-184">ABWQ 服務的查詢包含下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="8f6c2-185">**PhotoHash**   二進位相片資料的雜湊值，並使用它來判斷目前的相片是否已變更。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="8f6c2-186">**PhotoRelPath**   儲存在伺服器上的圖像檔案相對路徑。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="8f6c2-187">**PhotoSize**   圖像檔案的大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="8f6c2-188">**TimeStamp**   上次從伺服器下載圖像檔案並複製到用戶端快取的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="8f6c2-189">接著，Lync 2010 用戶端在取得圖像檔案之後，會將從查詢所傳回的屬性值與用戶端從區段內的配置中接收的屬性值進行比較，以查看它們是否不同。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="8f6c2-190">如果值不同，用戶端會使用 HTTP 取得請求來檢索登入使用者的圖像檔案。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="8f6c2-191">此外，用戶端會在每24小時從已建立圖像檔案的快取時間，並與用戶端上的值比較伺服器上的**PhotoHash**屬性值。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="8f6c2-192">如果值不同，用戶端會知道圖像檔案已變更。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="8f6c2-193">若要取得更新的圖像檔案，用戶端會重新查詢 ABWQ 服務，以更新用戶端快取中的映射檔與伺服器上的映射檔，也就是在用戶端快取中重設檔案上的**時間戳記**。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="8f6c2-194">下列是 ABWQ 服務查詢的範例回應：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-194">The following is an example response to a query to the ABWQ service:</span></span>
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

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="8f6c2-195">Lync 2013 中的使用者相片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-195">User photos in Lync 2013</span></span>

<span data-ttu-id="8f6c2-196">Lync 2013 為使用者相片推出高解析度影像的支援。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="8f6c2-197">Lync 2013 也提供支援，可將使用者相片儲存在 Exchange 2013 上的使用者信箱中，這會移除 Lync 2010 中存在的影像解析度和大小限制。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="8f6c2-198">在 Lync 2013 中的使用者相片，最多可有648圖元的648圖元，檔案大小最大為 20 MB。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="8f6c2-199">Lync 2013 中的高解析度相片必須位於 Exchange 2013 的使用者信箱中，而且只有 Lync 2013 用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="8f6c2-200">這項與 Exchange 的整合會利用2013版本的 Lync、Exchange 和 SharePoint 中所包含的新授權架構（即「Oauth」）。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="8f6c2-201">如果 Exchange 2013 未在您的部署中使用，則對使用者相片的支援與 Lync 2010 完全相同。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="8f6c2-202">不過，在 Lync 2013 用戶端中選擇要使用的相片的使用者選項會有所不同。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="8f6c2-203">在 Lync 2013 用戶端中，使用者可以選取 [**隱藏我的圖片**] 或 [**顯示我的圖片**]。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="8f6c2-204">預設不提供**從網站顯示圖片**的選項，但可以指派用戶端原則來啟用。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="8f6c2-205">隱藏我的圖片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-205">Hide my picture</span></span>

<span data-ttu-id="8f6c2-206">使用者相片的設定在 Lync 2013 的 [**選項**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="8f6c2-207">當您選擇 [**隱藏我的圖片**] 時，系統不會針對您的 lync 用戶端顯示任何使用者相片，但您的相片仍會顯示在您的連絡人卡片上，且在 lync 以外。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="8f6c2-208">顯示我的圖片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-208">Show my picture</span></span>

<span data-ttu-id="8f6c2-209">當您選擇 [**顯示我的圖片**] 選項時，您的使用者相片會顯示在您的 lync 用戶端，以及 lync 交談中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="8f6c2-210">所使用的圖像是儲存在 AD DS 中的影像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="8f6c2-211">顯示網站上的圖片</span><span class="sxs-lookup"><span data-stu-id="8f6c2-211">Show a picture from a website</span></span>

<span data-ttu-id="8f6c2-212">在用戶端原則設定為啟用之後，Lync 2013 中就會提供 [**從網站顯示圖片**] 選項。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="8f6c2-213">用戶端版本必須比15.0.4535.1002 安裝的版本必須更新，且與[Lync 累積更新：2013年11月](http://go.microsoft.com/fwlink/p/?linkid=509908)。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="8f6c2-214">使用者可能需要登出後再重新登入，以查看用戶端中的變更。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="8f6c2-215">您可以在 Lync Server 管理命令介面中執行 [[設定 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)原則]，將用戶端原則設定為 [啟用] 以**顯示來自網站**設定的圖片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="8f6c2-216">下列範例 Cmdlet 示範如何針對您部署中的所有使用者全域設定原則：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

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


<span data-ttu-id="8f6c2-217">當圖像上傳到使用者的信箱時，Exchange 會自動建立可在用戶端應用程式中使用的影像較低解析度版本。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="8f6c2-218">使用者相片也會在 AD DS 中更新。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="8f6c2-219">在 AD DS 中更新影像檔案時，會建立 48 x 48 圖元的影像，並用於 AD DS 中的 thumbnailPhoto。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="8f6c2-220">任何現有的圖像都會被取代。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-220">Any existing image is replaced.</span></span> <span data-ttu-id="8f6c2-221">因此，如果您已將 96 x 96 影像新增到 AD DS，就會使用新的 48 x 48 影像來覆寫它。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="8f6c2-222">這只是重要的一點，就是您在您的環境中擁有 Lync 2010 用戶端的使用者，因為這些用戶端會從 AD DS 取得使用者相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="8f6c2-223">如果您的組織中有 Lync 2010 用戶端，您可以匯入 96 x 96 圖元影像，以取代 AD DS 所建立的圖像。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="8f6c2-224">Lync 2013 中的使用者相片支援</span><span class="sxs-lookup"><span data-stu-id="8f6c2-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="8f6c2-225">在 Lync 2013 中，使用者相片支援三種影像解析度，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="8f6c2-226">所使用的影像是由指派給 Lync 使用者的用戶端原則設定所決定。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="8f6c2-227">如需詳細資訊，請參閱本主題中的 [使用用戶端策略 Cmdlet 管理使用者的相片]。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f6c2-228">圖像解析度（圖元）</span><span class="sxs-lookup"><span data-stu-id="8f6c2-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="8f6c2-229">應用程式</span><span class="sxs-lookup"><span data-stu-id="8f6c2-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f6c2-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="8f6c2-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-231">如果沒有選取較高的解析度圖像，就會使用</span><span class="sxs-lookup"><span data-stu-id="8f6c2-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f6c2-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="8f6c2-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-233">在 Outlook Web App 和 Outlook 2013 中使用</span><span class="sxs-lookup"><span data-stu-id="8f6c2-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f6c2-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="8f6c2-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="8f6c2-235">在 Lync 2013 桌面用戶端和 Lync 2013 Web App 中使用</span><span class="sxs-lookup"><span data-stu-id="8f6c2-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f6c2-236">任何在 Exchange 2013 中啟用信箱的使用者，都可以透過 Outlook Web Access 或 Lync 2013 用戶端選項上傳不同的影像，包括高解析度相片。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="8f6c2-237">使用的影像建議設定包括：</span><span class="sxs-lookup"><span data-stu-id="8f6c2-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="8f6c2-238">**圖像解析度**   648 乘以648圖元</span><span class="sxs-lookup"><span data-stu-id="8f6c2-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="8f6c2-239">**色深**   24 位</span><span class="sxs-lookup"><span data-stu-id="8f6c2-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="8f6c2-240">**影像檔案大小**   最大為 20 MB</span><span class="sxs-lookup"><span data-stu-id="8f6c2-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="8f6c2-241">**JPEG 檔案格式**   </span><span class="sxs-lookup"><span data-stu-id="8f6c2-241">**File format**   JPEG</span></span>

<span data-ttu-id="8f6c2-242">648圖元乘648圖元的典型24位 JPEG 影像的檔案大小為大約 240 KB，所以每4個使用者相片都需要 1 MB 的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="8f6c2-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

