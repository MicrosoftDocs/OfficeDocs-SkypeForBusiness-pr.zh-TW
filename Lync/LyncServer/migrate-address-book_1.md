---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52ca2b4882eec8b34ec07aa4e9365b6f444edd26
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="feaaa-102">移轉通訊錄</span><span class="sxs-lookup"><span data-stu-id="feaaa-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feaaa-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="feaaa-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="feaaa-104">**移轉通訊錄自訂正規化規則**</span><span class="sxs-lookup"><span data-stu-id="feaaa-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="feaaa-105">尋找公司\_電話\_號碼\_正規化\_Rules.txt 檔案通訊錄共用資料夾的根目錄中，並將它複製到 Lync Server 2013 試驗集區中通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="feaaa-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="feaaa-106">範例通訊錄正規化規則已安裝在您 ABS Web 元件的檔案目錄中。</span><span class="sxs-lookup"><span data-stu-id="feaaa-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="feaaa-107">路徑是<STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013\Web Components\Address 通訊錄 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt，</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="feaaa-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="feaaa-108">要複製此檔案，然後重新命名為&nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;至通訊錄共用的資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="feaaa-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="feaaa-109">例如，通訊錄共用<STRONG>$serverX</STRONG>，&nbsp;路徑會類似： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="feaaa-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="feaaa-110">使用文字編輯器，例如 「 記事本 」，若要開啟 [公司\_電話\_號碼\_正規化\_Rules.txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="feaaa-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="feaaa-111">Lync Server 2013 中，某些類型的項目將無法正確運作。</span><span class="sxs-lookup"><span data-stu-id="feaaa-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="feaaa-112">查看的這個步驟中所述的項目類型的檔案，視需要編輯這些，將變更儲存至試驗集區中通訊錄共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="feaaa-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="feaaa-113">包含必要的空白字元或標點符號原因正規化規則失敗，因為這些字元會移除超出輸入正規化規則的字串的字串。</span><span class="sxs-lookup"><span data-stu-id="feaaa-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="feaaa-114">如果您有包含必要的空白字元或標點符號的字串，您要修改的字串。</span><span class="sxs-lookup"><span data-stu-id="feaaa-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="feaaa-115">例如，下列字串會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="feaaa-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="feaaa-116">下列字串將不會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="feaaa-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

