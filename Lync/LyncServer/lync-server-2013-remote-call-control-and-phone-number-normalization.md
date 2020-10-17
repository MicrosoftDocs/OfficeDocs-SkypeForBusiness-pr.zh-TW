---
title: Lync Server 2013：遠端呼叫控制和電話號碼標準化
description: Lync Server 2013：遠端呼叫控制和電話號碼標準化。
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
ms.openlocfilehash: edcb50678da7111aba066745bce5e356dd1ac7f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555809"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="1baec-103">Lync Server 2013 的遠端呼叫控制和電話號碼正規化</span><span class="sxs-lookup"><span data-stu-id="1baec-103">Remote call control and phone number normalization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1baec-104">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="1baec-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="1baec-105">Lync 用戶端會下載電話號碼正規化規則，作為通訊錄服務的一部分 (ABS) 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="1baec-105">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="1baec-106">在遠端呼叫控制案例中，通訊錄服務電話號碼正規化規則會同時套用至撥入與撥出的遠端呼叫控制電話。</span><span class="sxs-lookup"><span data-stu-id="1baec-106">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="1baec-107">有來電撥打給已啟用遠端呼叫控制的使用者時，來電者的電話號碼會先由 SIP/CSTA 閘道或專用交換機 (PBX) 正規化為 E.164 格式。</span><span class="sxs-lookup"><span data-stu-id="1baec-107">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="1baec-108">當 Lync Server 2013 接收來自閘道的呼叫時，會針對來電者的 Microsoft Office Outlook 連絡人清單中的標準化號碼，或在通訊錄服務中儲存的全域通訊清單 (GAL) ，對來電者的電話號碼執行反向號碼查閱 (RNL) 。</span><span class="sxs-lookup"><span data-stu-id="1baec-108">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="1baec-109">如果反向號碼查閱順利找到相符項目，則會以來電通知中的名稱識別來電者。</span><span class="sxs-lookup"><span data-stu-id="1baec-109">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="1baec-110">對於撥出的遠端呼叫控制通話，Lync 會在將通話路由傳送至 SIP/CSTA 閘道之前，先將通訊錄服務電話號碼正規化規則套用至撥號的號碼。</span><span class="sxs-lookup"><span data-stu-id="1baec-110">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="1baec-111">如需建立遠端呼叫控制之電話號碼正規化規則的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的撥號對應表和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="1baec-111">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="1baec-112">移轉電話號碼正規化規則</span><span class="sxs-lookup"><span data-stu-id="1baec-112">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="1baec-113">如果您要移轉先前啟用遠端呼叫控制的使用者，請參閱移轉文件中的下列主題：</span><span class="sxs-lookup"><span data-stu-id="1baec-113">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="1baec-114">如需 Lync Server 2010，請參閱遷移檔中的 [遷移通訊錄](migrate-address-book.md) 。</span><span class="sxs-lookup"><span data-stu-id="1baec-114">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="1baec-115">如需通訊伺服器 2007 R2，請參閱遷移檔中的 [遷移通訊錄](migrate-address-book.md) 。</span><span class="sxs-lookup"><span data-stu-id="1baec-115">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

