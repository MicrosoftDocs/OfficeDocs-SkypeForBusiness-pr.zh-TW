---
title: Lync Server 2013：減少來路不明的 IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f8326d6fa9f85b202e0ea2dcbe3fed63a723aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="83c45-102">減少 Lync Server 2013 來路不明的 IM</span><span class="sxs-lookup"><span data-stu-id="83c45-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83c45-103">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="83c45-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="83c45-104">智慧 IM 篩選應用程式可協助保護您的 Microsoft Lync Server 2013 部署，以防範最常見的病毒，讓使用者體驗的效能降至最低。</span><span class="sxs-lookup"><span data-stu-id="83c45-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="83c45-105">[智慧 IM] 篩選提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="83c45-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="83c45-106">增強的 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="83c45-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="83c45-107">增強的檔案傳輸篩選</span><span class="sxs-lookup"><span data-stu-id="83c45-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="83c45-108">使用智慧 IM 篩選來設定篩選器，以封鎖來自公司防火牆以外的來自未知端點的未經請求或可能有害的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="83c45-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="83c45-109">您可以透過指定準則來決定要封鎖哪些專案（例如包含超連結的立即訊息，以及具有特定副檔名的檔案），來設定篩選。</span><span class="sxs-lookup"><span data-stu-id="83c45-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="83c45-110">在您部署智慧 IM 訊息篩選應用程式之前，您應該瞭解當郵件從一個 Lync Server 2013 伺服器路由到另一個時，如何套用篩選選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="83c45-111">套用這些篩選選項的方式是一致的，不論伺服器是位於單一組織中，還是跨組織界限。</span><span class="sxs-lookup"><span data-stu-id="83c45-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="83c45-112">這種一致性會套用至將自訂通知及警告文字插入郵件中並在伺服器之間傳送的方式。</span><span class="sxs-lookup"><span data-stu-id="83c45-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="83c45-113">[建議篩選] 選項可讓您在立即訊息中使用超連結，但必須先在其前面插入一個底線，才能停用連結。</span><span class="sxs-lookup"><span data-stu-id="83c45-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="83c45-114">如果您選擇此選項，您可以使用額外的選項，在每個包含超連結的立即訊息開頭顯示一則使用者。</span><span class="sxs-lookup"><span data-stu-id="83c45-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="83c45-115">第二個篩選選項是允許含有未修改超連結的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="83c45-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="83c45-116">如果您選擇此選項，您會有額外選項（建議），給插入在每封郵件中的使用者撰寫警告。</span><span class="sxs-lookup"><span data-stu-id="83c45-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="83c45-117">第三個選項是封鎖所有包含超連結的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="83c45-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="83c45-118">如果您選擇此選項，伺服器會將警告傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="83c45-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="83c45-119">您必須撰寫此警告。</span><span class="sxs-lookup"><span data-stu-id="83c45-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

