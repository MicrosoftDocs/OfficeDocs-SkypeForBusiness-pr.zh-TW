---
title: 在商務用 Skype Server 中設定高解析度相片的使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 摘要：在 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 和商務用 Skype Server 中設定高解析度相片的使用。
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834003"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="8327f-103">在商務用 Skype Server 中設定高解析度相片的使用</span><span class="sxs-lookup"><span data-stu-id="8327f-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="8327f-104">**摘要：** 在 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 和商務用 Skype Server 中設定高解析度相片的使用。</span><span class="sxs-lookup"><span data-stu-id="8327f-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="8327f-105">在商務用 Skype Server 中，相片可以儲存在使用者的 Exchange Server 2019、Exchange Server 2016、Exchange Server 2013 或 Exchange Online 信箱中，其可讓相片大小高達648圖元的648圖元。</span><span class="sxs-lookup"><span data-stu-id="8327f-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="8327f-106">此外，Exchange Server 可以視需要自動調整這些照片的大小，以供不同的產品使用。</span><span class="sxs-lookup"><span data-stu-id="8327f-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="8327f-107">通常是指三種不同的相片大小和解析度：</span><span class="sxs-lookup"><span data-stu-id="8327f-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="8327f-108">64圖元 x 64 圖元，使用 Active Directory thumbnailPhoto 屬性的大小。</span><span class="sxs-lookup"><span data-stu-id="8327f-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="8327f-109">若您將相片上傳至 Exchange Server，Exchange 會自動建立64圖元乘以該相片的64圖元版本，並更新使用者的 thumbnailPhoto 屬性。</span><span class="sxs-lookup"><span data-stu-id="8327f-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="8327f-110">不過，請注意，reverse 不是 true：如果您手動更新 Active Directory 中的 thumbnailPhoto 屬性，使用者的 Exchange 信箱中的相片將不會自動更新。</span><span class="sxs-lookup"><span data-stu-id="8327f-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="8327f-111">96圖元 x 96 圖元，供 Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、商務用 Skype Web App 和商務用 Skype 使用。</span><span class="sxs-lookup"><span data-stu-id="8327f-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="8327f-112">648圖元 x 648 圖元，供商務用 Skype web app 商務用 skype Web app 使用。</span><span class="sxs-lookup"><span data-stu-id="8327f-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8327f-113">如果您有資源，建議您上傳 648 x 648 相片;，可提供任何 Office 2013 應用程式的最大解析度及最佳圖片品質。</span><span class="sxs-lookup"><span data-stu-id="8327f-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="8327f-114">每個大小為 648 x 648 且深度為24位的 JPEG 相片會產生大約 240 kb 的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="8327f-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="8327f-115">這表示每4個使用者相片需要大約 1 mb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="8327f-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="8327f-116">使用 Exchange Web 服務存取的高解析度相片可由執行 Outlook 2013 Web App 的使用者上傳;只允許使用者更新其自己的相片。</span><span class="sxs-lookup"><span data-stu-id="8327f-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="8327f-117">不過，系統管理員可以使用 Exchange 管理命令介面和一系列 Windows PowerShell 命令，更新任何使用者的相片，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8327f-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="8327f-118">上一個範例中的第一個命令會使用 `Get-Content` Cmdlet 讀取檔案 C:\Photos\Kenmyer.jpg 的內容，並將該資料儲存在名為 $photo 的變數中。</span><span class="sxs-lookup"><span data-stu-id="8327f-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="8327f-119">在第二個命令中，Exchange Cmdlet `Set-UserPhoto` 是用來上傳相片，並將該相片附加到 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8327f-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8327f-120">在此範例中，Ken Myer 的 Active Directory 顯示名稱是用來做為使用者帳戶身分識別。</span><span class="sxs-lookup"><span data-stu-id="8327f-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="8327f-121">您也可以使用其他識別碼（例如使用者的 SMTP 位址或其使用者主要名稱）來參考使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8327f-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="8327f-122">如需詳細資訊，請參閱 Set-UserPhoto Cmdlet 的檔 [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) 。</span><span class="sxs-lookup"><span data-stu-id="8327f-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="8327f-123">上傳相片不會像指派該相片到 Ken Myer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8327f-123">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="8327f-124">相反地，上載照片只會導致在 [Outlook Web App 選項] 頁面上顯示該相片的預覽。</span><span class="sxs-lookup"><span data-stu-id="8327f-124">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="8327f-125">若要將該相片實際指派給使用者帳戶，使用者必須按一下 [選項] 頁面上的 [ **儲存** ]，否則系統管理員必須執行範例中的第三個命令。</span><span class="sxs-lookup"><span data-stu-id="8327f-125">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="8327f-126">第三個命令使用 Save 參數將相片指派給 Ken Myer 的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="8327f-126">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="8327f-127">若要確認已將新相片指派給使用者帳戶，Ken Myer 可登入商務用 Skype，請選取 [ **選項**]，然後選取 [ **我的圖片**]。</span><span class="sxs-lookup"><span data-stu-id="8327f-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="8327f-128">新上傳的相片應顯示為 Ken 的個人照片。</span><span class="sxs-lookup"><span data-stu-id="8327f-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="8327f-129">或者，系統管理員可以啟動 Internet Explorer，並流覽至類似下列的 URL，以確認任何使用者的相片。</span><span class="sxs-lookup"><span data-stu-id="8327f-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="8327f-130">如果系統管理員可以使用 Internet Explorer 來查看照片，但是使用者無法在商務用 Skype 中查看其相片，可能是 Exchange Web 服務或 Exchange 自動探索服務的連線問題。</span><span class="sxs-lookup"><span data-stu-id="8327f-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="8327f-131">請注意，若要在商務用 Skype 中使用此相片，也不需要進行其他設定。</span><span class="sxs-lookup"><span data-stu-id="8327f-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="8327f-132">相反地，照片會在上傳後立即可用，而且已 `Set-UserPhoto` 執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8327f-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
