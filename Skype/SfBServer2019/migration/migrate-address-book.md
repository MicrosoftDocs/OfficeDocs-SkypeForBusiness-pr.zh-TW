---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 一般說來，通訊錄會隨拓撲一起遷移。 不過，如果您自訂舊版環境中的下列步驟，您可能需要執行一些後續遷移步驟：
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752835"
---
# <a name="migrate-address-book"></a><span data-ttu-id="8290a-104">移轉通訊錄</span><span class="sxs-lookup"><span data-stu-id="8290a-104">Migrate Address Book</span></span>

<span data-ttu-id="8290a-105">一般說來，通訊錄會隨拓撲一起遷移。</span><span class="sxs-lookup"><span data-stu-id="8290a-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="8290a-106">不過，如果您自訂舊版環境中的下列步驟，您可能需要執行一些後續遷移步驟：</span><span class="sxs-lookup"><span data-stu-id="8290a-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="8290a-107">自訂通訊錄正常化規則。</span><span class="sxs-lookup"><span data-stu-id="8290a-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="8290a-108">將**UseNormalizationRules**參數的預設值變更為 False。</span><span class="sxs-lookup"><span data-stu-id="8290a-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="8290a-109">**通訊錄正常化規則**</span><span class="sxs-lookup"><span data-stu-id="8290a-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="8290a-110">如果您自訂舊版環境中的通訊錄正規化規則，您必須將自訂規則遷移至試驗集區。</span><span class="sxs-lookup"><span data-stu-id="8290a-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="8290a-111">如果您未自訂通訊錄正規化規則，則表示您沒有任何可遷移的通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="8290a-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="8290a-112">商務用 Skype Server 2019 的預設正規化規則與舊版安裝的預設規則相同。</span><span class="sxs-lookup"><span data-stu-id="8290a-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="8290a-113">依照本節稍後的程式，遷移自訂的正規化規則。</span><span class="sxs-lookup"><span data-stu-id="8290a-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="8290a-114">如果您的組織使用遠端呼叫控制，且您自訂了通訊錄正規化規則，您必須先執行本主題中的程式，才能使用遠端呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="8290a-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="8290a-115">此程式需要 RTCUniversalServerAdmins 群組或同等權利的成員資格。</span><span class="sxs-lookup"><span data-stu-id="8290a-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="8290a-116">**UseNormalizationRules 設定為 False**</span><span class="sxs-lookup"><span data-stu-id="8290a-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="8290a-117">如果您將**UseNormalizationRules**的值設為 False，讓使用者可以使用在 Active Directory 網域服務中定義的電話號碼，而不需有商務用 Skype Server 2019 套用正規化規則，您必須將**UseNormalizationRules**和**IgnoreGenericRules**參數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="8290a-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="8290a-118">請依照本節稍後的程式將這些參數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="8290a-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="8290a-119">遷移通訊錄自訂正常化規則</span><span class="sxs-lookup"><span data-stu-id="8290a-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="8290a-120">在 [通訊錄] 共用資料夾的根目錄中尋找 Company_Phone_Number_Normalization_Rules.txt 檔案，並將它複製到商務用 Skype Server 2019 試驗集區中的通訊錄共用資料夾根目錄。</span><span class="sxs-lookup"><span data-stu-id="8290a-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8290a-121">您的 ABS 網頁元件檔案目錄中已安裝範例通訊錄正常化規則。</span><span class="sxs-lookup"><span data-stu-id="8290a-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="8290a-122">路徑為 **$installedDriveLetter： \Program Files\Microsoft 商務用 Skype Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**。</span><span class="sxs-lookup"><span data-stu-id="8290a-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="8290a-123">您可以將此檔案複製並重新命名為**Company_Phone_Number_Normalization_Rules.txt**通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="8290a-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="8290a-124">例如， **$serverX**中共用的通訊錄，該路徑會類似如下： \*\* \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*。</span><span class="sxs-lookup"><span data-stu-id="8290a-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="8290a-125">使用文字編輯器（如 [記事本]）開啟 Company_Phone_Number_Normalization_Rules.txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="8290a-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="8290a-126">在商務用 Skype Server 2019 中，某些類型的專案將無法正確運作。</span><span class="sxs-lookup"><span data-stu-id="8290a-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="8290a-127">查看此步驟中所述之專案類型的檔案，視需要進行編輯，然後將變更儲存至試驗集區中的通訊錄共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="8290a-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="8290a-128">包含必要空格或標點符號的字串會導致正規化規則失敗，因為這些字元會從輸入到正規化規則的字串中去掉。</span><span class="sxs-lookup"><span data-stu-id="8290a-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="8290a-129">如果您有包含必要空格或標點符號的字串，您必須修改字串。</span><span class="sxs-lookup"><span data-stu-id="8290a-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="8290a-130">例如，下列字串會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="8290a-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="8290a-131">下列字串將不會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="8290a-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="8290a-132">若要將 UseNormalizationRules 和 IgnoreGenericRules 設定為 true</span><span class="sxs-lookup"><span data-stu-id="8290a-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="8290a-133">啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [**商務用 skype 伺服器管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="8290a-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="8290a-134">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="8290a-134">Do one of the following:</span></span>

   - <span data-ttu-id="8290a-135">如果您的部署只包含商務用 Skype Server 2019，請在全域層級執行下列 Cmdlet，將**UseNormalizationRules**和**IgnoreGenericRules**的值變更為 True：</span><span class="sxs-lookup"><span data-stu-id="8290a-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="8290a-136">如果您的部署包含商務用 Skype Server 2019 和舊版安裝的組合，請執行下列 Cmdlet，並將其指派給拓撲中的每個商務用 Skype Server 2019 集區：</span><span class="sxs-lookup"><span data-stu-id="8290a-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="8290a-137">等候中央管理存放區的複寫在所有集區上進行。</span><span class="sxs-lookup"><span data-stu-id="8290a-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="8290a-138">修改電話正規化規則檔案 "Company_Phone_Number_Normalization_Rules.txt"，以供您的部署清除內容。</span><span class="sxs-lookup"><span data-stu-id="8290a-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="8290a-139">檔案位於各個商務用 Skype Server 2019 集區的檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="8290a-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8290a-140">如果檔案不存在，請建立名為 "Company_Phone_Number_Normalization_Rules.txt" 的空檔案。</span><span class="sxs-lookup"><span data-stu-id="8290a-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="8290a-141">請等候幾分鐘，讓所有前端集區讀取新的檔案。</span><span class="sxs-lookup"><span data-stu-id="8290a-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="8290a-142">在您部署中的每個商務用 Skype Server 2019 集區上執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8290a-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


