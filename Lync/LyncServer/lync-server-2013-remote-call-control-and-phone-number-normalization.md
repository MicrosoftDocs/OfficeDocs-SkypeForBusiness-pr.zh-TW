---
title: Lync Server 2013： 遠端呼叫控制和電話號碼正規化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7ffb386f6b565fc00b866072bfab6390bc8d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="87941-102">遠端呼叫控制和電話號碼正規化 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="87941-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87941-103">_**主題上次修改日期：** 2012年-09-22_</span><span class="sxs-lookup"><span data-stu-id="87941-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="87941-104">Lync 用戶端下載通訊錄服務 (ABS) 檔案下載的一部分的電話號碼正規化規則。</span><span class="sxs-lookup"><span data-stu-id="87941-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="87941-105">在遠端呼叫控制案例中，通訊錄服務電話號碼正規化規則會同時套用至撥入與撥出的遠端呼叫控制電話。</span><span class="sxs-lookup"><span data-stu-id="87941-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="87941-106">有來電撥打給已啟用遠端呼叫控制的使用者時，來電者的電話號碼會先由 SIP/CSTA 閘道或專用交換機 (PBX) 正規化為 E.164 格式。</span><span class="sxs-lookup"><span data-stu-id="87941-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="87941-107">當 Lync Server 2013 接收來自閘道的通話時，便會在受話者的 Microsoft Office Outlook 連絡人清單或會儲存在全域通訊清單 (GAL) 中的正規化數字針對來電者的電話號碼執行反向號碼查閱 (RNL)通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="87941-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="87941-108">如果反向號碼查閱順利找到相符項目，則會以來電通知中的名稱識別來電者。</span><span class="sxs-lookup"><span data-stu-id="87941-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="87941-109">對於撥出的遠端呼叫控制電話，Lync 會套用通訊錄服務電話號碼正規化規則之前將電話路由至 SIP/CSTA 閘道對撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="87941-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="87941-110">如需建立電話號碼正規化規則為遠端呼叫控制的詳細資訊，請參閱規劃文件中的[撥號對應表和 Lync Server 2013 中的正規化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="87941-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="87941-111">移轉電話號碼正規化規則</span><span class="sxs-lookup"><span data-stu-id="87941-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="87941-112">如果您要移轉先前啟用遠端呼叫控制的使用者，請參閱移轉文件中的下列主題：</span><span class="sxs-lookup"><span data-stu-id="87941-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="87941-113">Lync Server 2010，請參閱移轉文件中的[Migrate Address Book](migrate-address-book.md) 。</span><span class="sxs-lookup"><span data-stu-id="87941-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="87941-114">Communications Server 2007 R2，請參閱移轉文件中的[Migrate Address Book](migrate-address-book_1.md) 。</span><span class="sxs-lookup"><span data-stu-id="87941-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

