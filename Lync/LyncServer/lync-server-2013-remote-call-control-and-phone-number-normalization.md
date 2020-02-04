---
title: Lync Server 2013：遠端呼叫控制和電話號碼正規化
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
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="84302-102">Lync Server 2013 中的遠端呼叫控制和電話號碼正規化</span><span class="sxs-lookup"><span data-stu-id="84302-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84302-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="84302-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="84302-104">Lync 用戶端會在通訊錄服務（ABS）檔案下載中下載電話號碼正規化規則。</span><span class="sxs-lookup"><span data-stu-id="84302-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="84302-105">在遠端通話控制案例中，通訊錄服務電話號碼正規化規則會套用到內送和撥出的遠端通話控制通話。</span><span class="sxs-lookup"><span data-stu-id="84302-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="84302-106">對於已啟用遠端呼叫控制的使用者，來電的電話號碼會先以 SIP/CSTA 閘道或私人分支交換（PBX）的方式來正常化為. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="84302-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="84302-107">當 Lync Server 2013 從閘道接收呼叫時，會針對被呼叫者的 Microsoft Office Outlook 連絡人清單或全域通訊清單（GAL）中的標準化數位，在來電者的電話號碼上執行反向號碼查閱（RNL），並儲存在通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="84302-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="84302-108">如果 [反向號碼查閱] 成功找到一個相符專案，來電者就會在來電通知中以名稱來加以識別。</span><span class="sxs-lookup"><span data-stu-id="84302-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="84302-109">對於傳出的遠端通話控制通話，Lync 會在將呼叫傳送到 SIP/CSTA 閘道之前，將通訊錄服務電話號碼正規化規則套用至撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="84302-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="84302-110">如需建立遠端通話控制的電話號碼正規化規則的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="84302-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="84302-111">遷移電話號碼正規化規則</span><span class="sxs-lookup"><span data-stu-id="84302-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="84302-112">如果您要將先前啟用的使用者遷移至 [遠端通話] 控制，請參閱以下 [遷移] 檔中的主題：</span><span class="sxs-lookup"><span data-stu-id="84302-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="84302-113">針對 Lync Server 2010，請參閱遷移檔中的 [[遷移通訊錄](migrate-address-book.md)]。</span><span class="sxs-lookup"><span data-stu-id="84302-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="84302-114">針對通訊伺服器 2007 R2，請參閱遷移檔中的 [[遷移通訊錄](migrate-address-book_1.md)]。</span><span class="sxs-lookup"><span data-stu-id="84302-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

