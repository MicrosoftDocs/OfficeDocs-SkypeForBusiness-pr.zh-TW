---
title: Lync Server 2013：配置媒體埠範圍設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="3477a-102">在 Lync Server 2013 中配置媒體埠範圍設定</span><span class="sxs-lookup"><span data-stu-id="3477a-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3477a-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3477a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3477a-104">媒體埠範圍設定會顯著影響用戶端效能，應加以設定。</span><span class="sxs-lookup"><span data-stu-id="3477a-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="3477a-105">您可以使用 Lync Server 管理命令介面來設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="3477a-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="3477a-106">媒體埠範圍設定</span><span class="sxs-lookup"><span data-stu-id="3477a-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3477a-107">正在</span><span class="sxs-lookup"><span data-stu-id="3477a-107">Setting</span></span></th>
<th><span data-ttu-id="3477a-108">說明</span><span class="sxs-lookup"><span data-stu-id="3477a-108">Description</span></span></th>
<th><span data-ttu-id="3477a-109">Lync Server 管理命令介面 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3477a-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="3477a-110">Cmdlet 參數</span><span class="sxs-lookup"><span data-stu-id="3477a-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3477a-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="3477a-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="3477a-112">指定用戶端是否應該使用伺服器傳送的埠範圍來傳送媒體和傳送信號。</span><span class="sxs-lookup"><span data-stu-id="3477a-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="3477a-113">與 subvalues MinMediaPort 和 MaxMediaPort 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="3477a-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="3477a-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="3477a-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="3477a-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="3477a-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3477a-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="3477a-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="3477a-117">指定要用於媒體的起始埠號碼。</span><span class="sxs-lookup"><span data-stu-id="3477a-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="3477a-118">與 MaxMediaPort 結合，以指定埠的範圍。</span><span class="sxs-lookup"><span data-stu-id="3477a-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="3477a-119">建議的最小範圍是40埠。</span><span class="sxs-lookup"><span data-stu-id="3477a-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="3477a-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="3477a-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="3477a-121">ClientMediaPort （代表用戶端媒體要使用的起始埠號碼）</span><span class="sxs-lookup"><span data-stu-id="3477a-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3477a-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="3477a-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="3477a-123">指定要用於媒體的最高埠數。</span><span class="sxs-lookup"><span data-stu-id="3477a-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="3477a-124">與 MinMediaPort 結合，以指定埠的範圍。</span><span class="sxs-lookup"><span data-stu-id="3477a-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="3477a-125">建議的最小範圍是40埠。</span><span class="sxs-lookup"><span data-stu-id="3477a-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="3477a-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="3477a-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="3477a-127">ClientMediaPortRange （表示用戶端媒體可用的埠總數; 預設值為40）</span><span class="sxs-lookup"><span data-stu-id="3477a-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="3477a-128">若要設定媒體埠範圍設定</span><span class="sxs-lookup"><span data-stu-id="3477a-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="3477a-129">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="3477a-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3477a-130">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3477a-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="3477a-131">這個 Cmdlet 會傳回會議設定。</span><span class="sxs-lookup"><span data-stu-id="3477a-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="3477a-132">使用您要變更的參數和值來執行下列 Cmdlet （如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 管理命令介面檔）：</span><span class="sxs-lookup"><span data-stu-id="3477a-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3477a-133">您可以為特定網站建立其他的會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="3477a-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="3477a-134">將<STRONG>CsConferencingConfiguration</STRONG> Cmdlet 與網站身分識別搭配使用。</span><span class="sxs-lookup"><span data-stu-id="3477a-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="3477a-135">當您為網站建立新的會議配置設定時，網站設定會優先于全域設定。</span><span class="sxs-lookup"><span data-stu-id="3477a-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="3477a-136">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="3477a-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

