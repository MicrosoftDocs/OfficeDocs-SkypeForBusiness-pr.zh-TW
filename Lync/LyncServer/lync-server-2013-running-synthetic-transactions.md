---
title: Lync Server 2013： 執行綜合交易
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 448e96c03b554970b1ee92166908965ee2a6629c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="5ac7a-102">在 Lync Server 2013 中執行的綜合交易</span><span class="sxs-lookup"><span data-stu-id="5ac7a-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ac7a-103">_**上次修改主題：** 2014年-08-18_</span><span class="sxs-lookup"><span data-stu-id="5ac7a-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="5ac7a-104">綜合交易通常是以兩種方式進行。</span><span class="sxs-lookup"><span data-stu-id="5ac7a-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="5ac7a-105">您可以使用 CsHealthMonitoringConfiguration cmdlet 設定的測試使用者，其登錄器集區的每個。</span><span class="sxs-lookup"><span data-stu-id="5ac7a-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="5ac7a-106">這些測試使用者是一組已預先設定的綜合交易，搭配使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="5ac7a-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="5ac7a-107">（通常是這些是測試帳戶並不屬於實際使用者的帳戶）。與集區設定的測試使用者，您可以執行的綜合交易針對該集區不必指定的身分識別 （和提供的認證） 測試中所涉及的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="5ac7a-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="5ac7a-108">或者，您可以使用的實際使用者帳戶執行的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="5ac7a-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="5ac7a-109">例如，如果兩個使用者不能交換立即訊息，您無法執行綜合交易 （而不一組測試帳戶），使用這些兩個使用者帳戶，然後再試以診斷並解決問題。</span><span class="sxs-lookup"><span data-stu-id="5ac7a-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="5ac7a-110">如果您決定要進行使用實際使用者帳戶的綜合交易，您必須提供登入名稱和每個使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="5ac7a-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5ac7a-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ac7a-111">See Also</span></span>


[<span data-ttu-id="5ac7a-112">在 Lync Server 2013 中設定監看員節點測試使用者與組態設定</span><span class="sxs-lookup"><span data-stu-id="5ac7a-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="5ac7a-113">Lync Server 2013 中的綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="5ac7a-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

