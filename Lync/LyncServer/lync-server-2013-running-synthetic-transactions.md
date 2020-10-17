---
title: Lync Server 2013：執行綜合交易
description: Lync Server 2013：執行綜合交易。
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
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569349"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="4ffdb-103">在 Lync Server 2013 中執行綜合交易</span><span class="sxs-lookup"><span data-stu-id="4ffdb-103">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ffdb-104">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="4ffdb-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="4ffdb-105">綜合交易通常會以兩種方式執行。</span><span class="sxs-lookup"><span data-stu-id="4ffdb-105">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="4ffdb-106">您可以使用 CsHealthMonitoringConfiguration Cmdlet 為每個註冊機構集區設定測試使用者。</span><span class="sxs-lookup"><span data-stu-id="4ffdb-106">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="4ffdb-107">這些測試使用者是一組預先設定為搭配綜合交易使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="4ffdb-107">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="4ffdb-108"> (通常是測試帳戶，而不是屬於實際使用者的帳戶。 ) 搭配針對集區設定的測試使用者，您可以針對該集區執行綜合交易，而不必指定 (的身分識別，並提供認證，以) 測試所涉及的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4ffdb-108">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="4ffdb-109">或者，您可以使用實際的使用者帳戶執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="4ffdb-109">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="4ffdb-110">例如，如果兩位使用者無法 exchange 立即訊息，您可以使用這兩個使用者 (帳戶執行綜合交易，而不是) 一對測試帳戶，然後嘗試診斷並解決問題。</span><span class="sxs-lookup"><span data-stu-id="4ffdb-110">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="4ffdb-111">如果您決定使用實際使用者帳戶進行綜合交易，您必須為每位使用者提供登入名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="4ffdb-111">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4ffdb-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ffdb-112">See Also</span></span>


[<span data-ttu-id="4ffdb-113">在 Lync Server 2013 中設定監視節點測試使用者和設定設定</span><span class="sxs-lookup"><span data-stu-id="4ffdb-113">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="4ffdb-114">Lync Server 2013 中綜合交易的特殊設定指示</span><span class="sxs-lookup"><span data-stu-id="4ffdb-114">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

