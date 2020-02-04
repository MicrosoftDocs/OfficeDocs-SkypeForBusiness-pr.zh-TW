---
title: Lync Server 2013：規劃私人電話線路
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
ms.openlocfilehash: 0df93d8a8de73a3119e7ca9a1a7abd76e9157a17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>使用 Lync Server 2013 規劃私人電話線路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-11_

Lync Server 2013 也提供除了主要電話線之外，也可為使用者提供第二部、私人電話線的功能。 您通常會將私人電話線指派給主管人員，以及想要其直接達到未列出電話號碼的其他人。

私人電話線只能使用 Lync Server 管理命令介面來設定。 您無法使用 Lync Server [控制台] 設定私人電話線路。 私人電話線只能在 Lync Server 部署而不是混合式部署中進行設定。

<div>

## <a name="characteristics-of-private-telephone-lines"></a>私人電話線路的特性

雖然第二個是私人電話線的概念基本簡單，但請務必瞭解私人線路的特性，以及它們與使用者的主要電話線相似且不同的方式。

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>私人電話線路的一般特性

  - 一位使用者只能有一個私人電話線路。

  - 擁有私人電話線路的使用者只有一個語音信箱，而且會在單一電子郵件地址收到未接來電通知。

  - 擁有私人電話線的使用者沒有第二個 SIP 位址，第二個私人電話線不會給予使用者第二個在網路上的狀態（例如第二個立即訊息身分識別）。

  - 私人電話線只適用于內部部署部署。 它們無法用於 Lync Server 的託管部署。

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>私人電話線與主要電話線路有何不同

  - 私人電話線路的電話號碼不會出現在從 Active Directory 網域服務衍生的電話目錄或連絡人清單中。

  - 私人電話線不提供下列任何功能：來電轉接、團隊通話、委派、小組振鈴、群組通話，以及回應群組應用程式。

  - 呼叫私人電話線有特殊的響鈴，通話的系統通知會告訴使用者來電是在他或她的私人線路上。

  - 呼叫專用電話線路的電話總是會響鈴。 它們不會追蹤「請勿打擾」規則。

  - 私人電話線路僅供進貨，不能用來撥出電話。 當使用者使用私人電話線路撥打電話時，通話是從使用者的主要電話線發出，而且不會隱藏使用者的名稱或使用者的主要電話號碼（來自呼叫者）。

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>私人電話線與主要電話線路類似的方式

  - 對於主要電話線（如果已啟用語音信箱），會將未接聽的電話撥打電話至相同的語音信箱收件匣。

  - 通話駐留和通話裝貨使用私人電話線的方式與使用者的主要電話線完全相同。

  - 在使用者的主要電話線上啟用同時撥打時，也會在專線電話線路上啟用。

  - 私人電話線的電話號碼會以與使用者主要電話線的電話號碼相同的方式記錄在通話明細記錄中，但會指出它是私人電話號碼。

  - 使用者在私人電話線上接聽來電之後，該通話就會與使用者的主要電話線上的通話相同。 例如，如果在私人電話線路上接聽通話的使用者轉寄來電或邀請其他人加入電話會議，則使用者的名稱會出現在 Lync 2013 中，而使用者的主要電話線的電話號碼會顯示在本機號碼中。

  - 使用者可以使用與主要電話線相同的方式，在私人電話線上轉移通話（例如行動電話或家用電話，然後再以其他目的地（例如行動電話或家用電話）。
    
    <div>
    

    > [!NOTE]  
    > 當您將私人線路的呼叫路由到備用電話號碼時，備用電話線路的電話號碼會提供給備用電話號碼，而且可顯示在該號碼的記錄中。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在傳入系統通知中，從會議到私人電話線路的通話不會有<EM>私線</EM>指示。

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>管理私人電話線路

除了建立及管理私人電話線的技術方面，您必須為其建立管理程式。 這包括決定組織中誰符合私人線路、建立和維護人員及其電話線路的原則，可能會為主管建立私人的電話目錄、安排使用者訓練，以及相關工作。

<div>


> [!NOTE]  
> 私人電話線會儲存在 Active Directory 中，做為 user 物件上的 msRTCSIP-PrivateLine 屬性。 根據預設，[經過驗證的使用者] 群組的任何成員都有讀取這個屬性的許可權。



</div>

<div>

## <a name="assigning-telephone-numbers"></a>指派電話號碼

使用 Lync Server [控制台] 或 [Lync Server 管理命令介面]，以與不含私人電話線的帳戶相同的方式建立需要私人電話線之新使用者的帳戶。

在 Lync Server 管理命令介面中使用**move-csuser** Cmdlet，將電話號碼指派給使用者的私人電話線路，例如，**設定 move-csuser 身分 "Sip:joe@contoso.com"-PrivateLine "電話： + 14255551212"**。

私人電話線的電話號碼長度可以介於3到15個數字之間，且必須在前面加上「電話：」首碼。 只要您的組織有直接撥打該區號及國家/地區代碼，他們就可以有任何地區代碼及任何國家/地區的程式碼。

如需有關 Cmdlet 和 Lync Server 管理命令介面的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面檔。

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>混合式部署中的私人電話線路

私人電話線只應針對 Lync Server 的部署進行設定。 在其中同時有 Lync Server 和 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 伺服器的部署中，當較舊版本的使用者嘗試呼叫私人電話線時，呼叫路由失敗的原因是伺服器無法在私人電話線路上執行反向編號查閱。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

