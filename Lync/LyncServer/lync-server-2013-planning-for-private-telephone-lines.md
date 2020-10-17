---
title: Lync Server 2013：規劃私人電話線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5381d0f71dd6e15a3b4b6d76f2a03be558b9d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526520"
---
# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>使用 Lync Server 2013 規劃私人電話線

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-11_

Lync Server 2013 引進除了主要電話線之外，也可為使用者提供第二部私人電話線。 私人電話線通常會指派給主管人員和其他人，其可直接到達未列出的電話號碼。

私人電話線只能使用 Lync Server 管理命令介面來設定。 您無法使用 Lync Server [控制台] 設定私人電話線。 私人電話線應該只在部署 Lync Server 時設定，而不是在混合部署中設定。

<div>

## <a name="characteristics-of-private-telephone-lines"></a>私人電話線的特性

雖然第二個私人電話線的概念基本上很簡單，但是請務必瞭解私人線路的特性，以及它們與使用者的主要電話線的類似之處和不同之處的方式。

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>私人電話線的一般特性

  - 使用者只能有一個私人電話線。

  - 具有私人電話線的使用者只有一個語音信箱，並在單一電子郵件地址接收未接來電通知。

  - 具有私人電話線的使用者沒有第二個 SIP 位址，第二部私人電話線不會讓使用者在網路上有第二個存在的狀態 (例如，第二個立即訊息身分識別) 。

  - 私人電話線只適用于內部部署部署。 它們不適用於 Lync Server 的託管部署。

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>私人電話線與主要電話線的區別

  - 私人電話線的電話號碼不會出現在從 Active Directory 網域服務衍生的電話目錄或連絡人清單中。

  - 私人電話線沒有下列任何功能：「來電轉接」、「小組通話」、「委派」、「小組振鈴」、「群組通話挑選」和「回應群組」應用程式。

  - 撥打私人電話線的電話有特殊的震鈴，而且呼叫的系統通知會告訴使用者，來電是在其私人線路上。

  - 對私人電話線的來電一定會來電。 它們不遵循「請勿打擾」規則。

  - 私人電話線只是輸入，無法用來撥打撥出電話。 當具有私人電話線的使用者撥打通話時，此呼叫來自使用者的主要電話線，而且不會隱藏使用者的名稱或使用者的主要電話號碼（來自呼叫者）。

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>私人電話線與主要電話線的相似之處

  - 對私人電話線的未接聽呼叫會路由傳送至與主要電話線 (，如果已啟用語音信箱) 中的 [語音信箱] 收件匣。

  - 通話駐留及呼叫收取的運作方式與私人電話線完全相同，與使用者的主要電話線相同。

  - 在使用者的主要電話線上啟用同時震鈴時，也會在私人電話線上啟用同時震鈴。

  - 私人電話線的電話號碼會記錄在通話詳細資料記錄中，其方式與使用者主要電話線的電話號碼相同，但是會指出其為私人電話號碼。

  - 在使用者接聽私人電話線上的來電之後，通話會與使用者的主要電話線上的呼叫進行相同的處理。 例如，如果接收私人電話線上之來電的使用者轉寄來電或邀請其他人加入電話會議，使用者的名稱會出現在 Lync 2013 中，而且使用者主要電話線的電話號碼會顯示在來電者識別碼中。

  - 使用者可以轉移來電 (將來電重新導向至另一個目的地（如行動電話或住家電話），再以與主要電話線相同的方式，從私人電話線進行回應) 。
    
    <div>
    

    > [!NOTE]  
    > 當私人線路呼叫路由傳送至其他電話號碼時，可將私人電話線的電話號碼提供給其他電話號碼，並顯示在該號碼的記錄檔中。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 從會議到私人電話線的呼叫，在傳入系統通知中不會有 <EM>私密金鑰</EM> 指示。

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>管理私人電話線

除了建立及管理私人電話線的技術層面之外，您還需要為他們建立系統管理程式。 這包括決定組織中誰符合私人行的原則、建立及維護人員及其電話線的清單，可能會為主管人員建立私人的電話目錄，以及為使用者訓練進行安排，以及相關的任務。

<div>


> [!NOTE]  
> 私人電話線會儲存在 Active Directory 中，做為使用者物件上的 msRTCSIP-PrivateLine 屬性。 根據預設，已驗證使用者群組的任何成員都具有此屬性的讀取權限。



</div>

<div>

## <a name="assigning-telephone-numbers"></a>指派電話號碼

使用 Lync Server 控制台或 Lync Server 管理命令介面，以與不含私人電話線的帳戶相同的方式，建立需要私人電話線之新使用者的帳戶。

使用 Lync Server 管理命令介面中的 **Set-CsUser** Cmdlet，將電話號碼指派給使用者的私人電話線，例如 **Set-CsUser 身分 "sip:joe@contoso.com"-PrivateLine "電話： + 14255551212"**。

私人電話線的電話號碼長度可以介於3到15個數字之間，且前面必須加上 "TEL:" 前置詞。 只要您的組織對該區號和國家/地區碼進行直接撥號，他們就可以擁有任何區功能變數代碼和任何國家/地區碼。

如需 Cmdlet 和 Lync Server 管理命令介面的詳細資訊，請參閱 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面檔。

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>混合式部署中的私人電話線

私人電話線應該只針對 Lync Server 的部署進行設定。 在具有 Lync Server 和 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 伺服器的部署中，當舊版使用者嘗試撥打私人電話線時，路由呼叫會失敗，因為伺服器無法在私人電話線上執行反向號碼查閱。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

