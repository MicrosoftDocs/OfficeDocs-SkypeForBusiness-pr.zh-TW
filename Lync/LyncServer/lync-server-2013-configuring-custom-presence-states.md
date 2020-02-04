---
title: Lync Server 2013：設定自訂的目前狀態
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
ms.openlocfilehash: c69f7a5b32b4ad0dd31f8be118aa2f2173ff3e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="47115-102">在 Lync Server 2013 中設定自訂的目前狀態</span><span class="sxs-lookup"><span data-stu-id="47115-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47115-103">_**主題上次修改日期：** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="47115-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="47115-104">若要在 Lync 2013 中定義自訂的目前狀態，請建立 XML 自訂目前設定檔案，然後使用**CSClientPolicy**或**CSClientPolicy**參數 CustomStateURL 的 Lync Server Management Shell Cmdlet 來指定其位置。</span><span class="sxs-lookup"><span data-stu-id="47115-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="47115-105">設定檔具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="47115-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="47115-106">您可以使用 [可用]、[忙碌] 和 [請勿打擾] 目前狀態指示器來設定自訂的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="47115-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="47115-107">Availability 屬性會判斷哪個目前狀態標記與自訂狀態的狀態文字相關聯。</span><span class="sxs-lookup"><span data-stu-id="47115-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="47115-108">在本主題稍後的範例中，[從家用版工作] 的狀態文字會顯示在綠色（可用）目前狀態指示器的右側。</span><span class="sxs-lookup"><span data-stu-id="47115-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="47115-109">狀態文字的最大長度為64個字元。</span><span class="sxs-lookup"><span data-stu-id="47115-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="47115-110">最多可以新增四個自訂目前狀態。</span><span class="sxs-lookup"><span data-stu-id="47115-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="47115-111">CustomStateURL 參數會指定設定檔的位置。</span><span class="sxs-lookup"><span data-stu-id="47115-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="47115-112">在 Lync 2013 中，SIP 高安全性模式預設為啟用，因此您必須將自訂目前狀態設定檔案儲存在已啟用 HTTPS 的 web 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="47115-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="47115-113">否則，Lync 2013 用戶端將無法與其連線。</span><span class="sxs-lookup"><span data-stu-id="47115-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="47115-114">例如，有效的位址就是`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`。</span><span class="sxs-lookup"><span data-stu-id="47115-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47115-115">雖然在生產環境中不建議這樣做，但您可以在用戶端上使用 EnableSIPHighSecurityMode 登錄設定來停用 SIP 高安全性模式，來測試位於非 HTTPS 檔案共用上的設定檔。</span><span class="sxs-lookup"><span data-stu-id="47115-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="47115-116">接著，您可以使用 CustomStateURL 登錄設定來指定設定檔的非 HTTPS 位置。</span><span class="sxs-lookup"><span data-stu-id="47115-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="47115-117">請注意，Lync 2013 會說明 Lync 2010 登錄設定，但已更新註冊表配置單元。</span><span class="sxs-lookup"><span data-stu-id="47115-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="47115-118">您會建立如下所示的註冊表設定：</span><span class="sxs-lookup"><span data-stu-id="47115-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="47115-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="47115-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="47115-120">類型： DWORD</span><span class="sxs-lookup"><span data-stu-id="47115-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="47115-121">值資料：0</span><span class="sxs-lookup"><span data-stu-id="47115-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="47115-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="47115-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="47115-123">類型： String （REG_SZ）</span><span class="sxs-lookup"><span data-stu-id="47115-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="47115-124">值資料（範例）： file://\\lspool. com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="47115-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="47115-125">在 XML 設定檔中指定一個或多個地區識別碼（LCID）架構，以當地語系化您的自訂目前狀態。</span><span class="sxs-lookup"><span data-stu-id="47115-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="47115-126">本主題稍後的範例會將當地語系化顯示為英文-美國（1033）、挪威文（1044）、法文-法國（1036）及土耳其文（1055）。</span><span class="sxs-lookup"><span data-stu-id="47115-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="47115-127">如需 Lcid 的清單，請參閱 Microsoft 所指派的地區<http://go.microsoft.com/fwlink/p/?linkid=157331>識別碼。</span><span class="sxs-lookup"><span data-stu-id="47115-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="47115-128">若要將自訂目前狀態新增至 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="47115-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="47115-129">建立使用下列範例格式的 XML 設定檔：</span><span class="sxs-lookup"><span data-stu-id="47115-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
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

2.  <span data-ttu-id="47115-130">將 XML 設定檔儲存到已啟用 HTTPS 的 web 伺服器。</span><span class="sxs-lookup"><span data-stu-id="47115-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="47115-131">在這個範例中，檔案稱為 [目前狀態 .xml] 並儲存在位置https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml。</span><span class="sxs-lookup"><span data-stu-id="47115-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="47115-132">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="47115-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="47115-133">在 Lync Server 管理命令介面中，使用類似下列的命令來定義 XML 設定檔的位置：</span><span class="sxs-lookup"><span data-stu-id="47115-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="47115-134">使用**授與 CSClientPolicy** Cmdlet 將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="47115-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="47115-135">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[新 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)與[授與 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="47115-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="47115-136">依預設，Lync Server 2013&nbsp;會每隔三小時更新一次用戶端原則和設定。</span><span class="sxs-lookup"><span data-stu-id="47115-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="47115-137">如果您想要繼續使用舊版版本（例如 CustomStateURL）的群組原則設定，Lync 2013 會辨識這些設定（如果它們位於新的 Policy registry 配置單元（HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync）中。</span><span class="sxs-lookup"><span data-stu-id="47115-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="47115-138">不過，以伺服器為基礎的用戶端原則優先。</span><span class="sxs-lookup"><span data-stu-id="47115-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

