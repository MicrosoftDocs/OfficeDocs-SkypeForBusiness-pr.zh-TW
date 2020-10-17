---
title: Lync Server 2013：設定自訂顯示狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd551ede7d7be7e631c229e99613cfc8baa006eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526990"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="815bb-102">在 Lync Server 2013 中設定自訂的顯示狀態</span><span class="sxs-lookup"><span data-stu-id="815bb-102">Configuring custom presence states in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="815bb-103">_**主題上次修改日期：** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="815bb-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="815bb-104">若要在 Lync 2013 中定義自訂的顯示狀態，請建立 XML 自訂的顯示設定檔，然後使用 Lync Server 管理命令介面 Cmdlet **New-CSClientPolicy** 或 **Set-CSClientPolicy** 參數 CustomStateURL 來指定其位置。</span><span class="sxs-lookup"><span data-stu-id="815bb-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="815bb-105">設定檔具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="815bb-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="815bb-106">您可以使用 [可用、忙碌] 和 [請勿打擾] 顯示狀態指標來設定自訂顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="815bb-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="815bb-107">Availability 屬性決定與自訂狀態的狀態文字相關聯的目前狀態指示器。</span><span class="sxs-lookup"><span data-stu-id="815bb-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="815bb-108">在本主題稍後的範例中，會在綠色 (可用) 顯示狀態指示器的右側顯示「住宅工作」的狀態文字。</span><span class="sxs-lookup"><span data-stu-id="815bb-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="815bb-109">狀態文字的最大長度為64個字元。</span><span class="sxs-lookup"><span data-stu-id="815bb-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="815bb-110">最多可新增四個自訂的顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="815bb-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="815bb-111">CustomStateURL 參數會指定設定檔的位置。</span><span class="sxs-lookup"><span data-stu-id="815bb-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="815bb-112">在 Lync 2013 中，SIP 高安全性模式預設為啟用，因此您需要將自訂目前狀態設定檔儲存在已啟用 HTTPS 的網頁伺服器上。</span><span class="sxs-lookup"><span data-stu-id="815bb-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="815bb-113">否則，Lync 2013 用戶端將無法與其連線。</span><span class="sxs-lookup"><span data-stu-id="815bb-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="815bb-114">例如，有效的位址是 `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` 。</span><span class="sxs-lookup"><span data-stu-id="815bb-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="815bb-115">雖然在實際執行環境中不建議使用此方法，但您可以在非 HTTPS 檔案共用上測試組態檔，方法是使用 EnableSIPHighSecurityMode 登錄設定，以停用用戶端的 SIP 高安全性模式。</span><span class="sxs-lookup"><span data-stu-id="815bb-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="815bb-116">然後，您可以使用 CustomStateURL 登錄設定來指定設定檔的非 HTTPS 位置。</span><span class="sxs-lookup"><span data-stu-id="815bb-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="815bb-117">請注意，Lync 2013 會考慮 Lync 2010 登錄設定，但是登錄蜂巢已更新。</span><span class="sxs-lookup"><span data-stu-id="815bb-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="815bb-118">您可以建立登錄設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="815bb-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="815bb-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="815bb-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="815bb-120">類型：DWORD</span><span class="sxs-lookup"><span data-stu-id="815bb-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="815bb-121">值資料：0</span><span class="sxs-lookup"><span data-stu-id="815bb-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="815bb-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="815bb-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="815bb-123">Type： String (REG_SZ) </span><span class="sxs-lookup"><span data-stu-id="815bb-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="815bb-124">數值資料 (範例) ： file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="815bb-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="815bb-125">在 XML 設定檔中，指定一或多個地區識別碼 (LCID) 架構，以當地語系化您的自訂狀態狀態。</span><span class="sxs-lookup"><span data-stu-id="815bb-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="815bb-126">本主題稍後的範例會在 1033) 、挪威文（博克瑪律性） (1044) 中，French-France (1036) ，以及土耳其文 (1055) ，將當地語系化展示為英文的美國 (</span><span class="sxs-lookup"><span data-stu-id="815bb-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="815bb-127">如需 Lcid 的清單，請參閱由 Microsoft 所指派的地區設定 IDs <https://go.microsoft.com/fwlink/p/?linkid=157331> 。</span><span class="sxs-lookup"><span data-stu-id="815bb-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="815bb-128">若要將自訂目前狀態新增至 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="815bb-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="815bb-129">建立使用下列範例格式的 XML 設定檔：</span><span class="sxs-lookup"><span data-stu-id="815bb-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="815bb-130">將 XML 設定檔儲存到啟用 HTTPS 的網頁伺服器。</span><span class="sxs-lookup"><span data-stu-id="815bb-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="815bb-131">在此範例中，會將檔案命名為 Presence.xml，並將其儲存至該位置 https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml 。</span><span class="sxs-lookup"><span data-stu-id="815bb-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="815bb-132">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="815bb-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="815bb-133">在 Lync Server 管理命令介面中，使用類似下列的命令，定義 XML 設定檔的位置：</span><span class="sxs-lookup"><span data-stu-id="815bb-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="815bb-134">使用 **Grant-CSClientPolicy** Cmdlet 將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="815bb-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="815bb-135">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 和 [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="815bb-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="815bb-136">Lync Server 2013 預設會 &nbsp; 每三個小時更新一次用戶端原則和設定。</span><span class="sxs-lookup"><span data-stu-id="815bb-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="815bb-137">如果您想要繼續使用舊版本的群組原則設定，例如 CustomStateURL，當 Lync 2013 位於新原則登錄蜂巢 ( # A0 時，將會辨識設定。</span><span class="sxs-lookup"><span data-stu-id="815bb-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="815bb-138">不過，以伺服器為基礎的用戶端原則會優先。</span><span class="sxs-lookup"><span data-stu-id="815bb-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

