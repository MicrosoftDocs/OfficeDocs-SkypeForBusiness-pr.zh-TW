---
title: 在商務用 Skype Server 中進行樹系準備所進行的變更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本節將說明樹系準備步驟所建立的全域設定與物件，以及萬用服務和管理群組。
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831913"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="b5ea2-103">在商務用 Skype Server 中進行樹系準備所進行的變更</span><span class="sxs-lookup"><span data-stu-id="b5ea2-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="b5ea2-104">本節將說明樹系準備步驟所建立的全域設定與物件，以及萬用服務和管理群組。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="b5ea2-105">Active Directory 全域設定和物件</span><span class="sxs-lookup"><span data-stu-id="b5ea2-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="b5ea2-106">如果您將全域設定儲存在設定容器中 () 所有新的商務用 Skype Server 部署的案例，樹系準備會使用現有的服務容器，並在 Configuration\Services 物件底下新增 **RTC 服務** 物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="b5ea2-107">在 RTC 服務物件下，樹系準備會新增 msRTCSIP-GlobalContainer 類型的 **Global Settings** 物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="b5ea2-108">全域設定物件會包含套用至商務用 Skype Server 部署的所有設定。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="b5ea2-109">如果您將全域設定儲存在「系統」容器中，則樹系準備會使用根網域「系統」容器下的 Microsoft 容器，並在 System\Microsoft 物件下新增 RTC 服務物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="b5ea2-110">樹系準備也會針對執行程序的根網域，新增 **msRTCSIP-Domain** 物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="b5ea2-111">Active Directory 萬用服務和管理群組</span><span class="sxs-lookup"><span data-stu-id="b5ea2-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="b5ea2-p102">樹系準備也會根據您指定的網域建立萬用群組，並為這些群組新增存取控制項目 (ACE)。這個步驟會在您指定之網域的使用者容器中，建立萬用群組。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="b5ea2-p103">萬用群組允許管理員存取以及管理全域設定和服務。樹系準備會新增下列類型的萬用群組：</span><span class="sxs-lookup"><span data-stu-id="b5ea2-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="b5ea2-116">系統 **管理群組** 這些群組會為商務用 Skype Server 網路定義系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="b5ea2-117">**基礎結構群組** 這些群組提供存取商務用 Skype Server 基礎結構特定區域的許可權。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="b5ea2-118">它們可做為系統管理群組元件的功能來運作。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-118">They function as components of administrative groups.</span></span> <span data-ttu-id="b5ea2-119">您不應該修改這些群組或將使用者直接新增至這些群組中。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="b5ea2-120">**服務群組** 這些群組是存取各種商務用 Skype Server 服務所需的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="b5ea2-121">下表說明系統管理群組。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="b5ea2-122">**樹系準備時建立的系統管理群組**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="b5ea2-123">**系統管理群組**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-123">**Administrative group**</span></span>|<span data-ttu-id="b5ea2-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5ea2-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b5ea2-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="b5ea2-126">允許成員管理伺服器和集區設定，包括所有伺服器角色、全域設定以及使用者。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b5ea2-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="b5ea2-128">可讓成員管理使用者設定，也可以將使用者從一個伺服器或集區移到另一個伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="b5ea2-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="b5ea2-130">可讓成員讀取伺服器、集區和使用者設定。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="b5ea2-131">下表說明基礎結構群組。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="b5ea2-132">**樹系準備時建立的基礎結構群組**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="b5ea2-133">**基礎結構群組**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-133">**Infrastructure group**</span></span>|<span data-ttu-id="b5ea2-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5ea2-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="b5ea2-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="b5ea2-136">授與商務用 Skype Server 之全域設定物件的寫入權限。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b5ea2-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="b5ea2-138">授與商務用 Skype Server 之全域設定物件的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b5ea2-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="b5ea2-140">授與商務用 Skype Server 使用者設定的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b5ea2-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="b5ea2-142">授與商務用 Skype 伺服器設定的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="b5ea2-143">這個群組沒有集區層級設定的存取權，只能存取個別伺服器特有的設定。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="b5ea2-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="b5ea2-145">授與商務用 Skype 伺服器設定的唯讀存取權，而且會放在安裝期間 survivable 分支裝置的本機系統管理員群組中。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="b5ea2-146">下表說明服務群組。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-146">The following table describes the service groups.</span></span>

<span data-ttu-id="b5ea2-147">**樹系準備時建立的服務群組**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="b5ea2-148">**服務群組**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-148">**Service group**</span></span>|<span data-ttu-id="b5ea2-149">**描述**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5ea2-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b5ea2-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="b5ea2-151">包含用於執行前端伺服器和 Standard Edition 伺服器的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="b5ea2-152">此群組可讓伺服器能夠讀取/寫入商務用 Skype Server 全域設定和 Active Directory 使用者物件的存取權。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b5ea2-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="b5ea2-154">包括用來執行 A/V 會議伺服器、Web 服務、轉送伺服器、封存伺服器及監控伺服器的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b5ea2-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="b5ea2-156">包含用來執行商務用 Skype Server Edge server 的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="b5ea2-158">包括可參與商務用 Skype Server 中央管理存放區複寫的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="b5ea2-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b5ea2-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="b5ea2-160">授與商務用 Skype 伺服器設定的唯讀存取權，但可用於設定 survivable branch server 和 survivable branch 裝置部署的安裝。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="b5ea2-161">接著，樹系準備會將服務和管理群組新增到適當的基礎結構群組，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b5ea2-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="b5ea2-162">新增 RTCUniversalServerAdmins 到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="b5ea2-163">新增 RTCUniversalUserAdmins 做為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="b5ea2-164">新增 RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 做為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="b5ea2-165">樹系準備也會建立下列角色型存取控制 (RBAC) 群組：</span><span class="sxs-lookup"><span data-stu-id="b5ea2-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="b5ea2-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-166">CSAdministrator</span></span>

- <span data-ttu-id="b5ea2-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="b5ea2-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="b5ea2-168">CSHelpDesk</span></span>

- <span data-ttu-id="b5ea2-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="b5ea2-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="b5ea2-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-171">CSServerAdministrator</span></span>

- <span data-ttu-id="b5ea2-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-172">CSUserAdministrator</span></span>

- <span data-ttu-id="b5ea2-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="b5ea2-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="b5ea2-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="b5ea2-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="b5ea2-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="b5ea2-176">CsResponseGroupManager</span></span>

<span data-ttu-id="b5ea2-177">如需 RBAC 角色以及各角色可執行的工作的詳細資訊，請參閱規劃文件中的＜[Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="b5ea2-178">樹系準備會同時建立私人與公用 ACE。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="b5ea2-179">它會在商務用 Skype Server 所使用的全域設定容器上建立專用 Ace。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="b5ea2-180">此容器只會由商務用 Skype 伺服器使用，而且可以位於設定容器或根域的系統容器中，視您儲存全域設定的位置而定。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="b5ea2-181">樹系準備所建立的公用 ACE 列於下表。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="b5ea2-182">**樹系準備建立的公用 ACE。**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="b5ea2-183">**Ace**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-183">**ACE**</span></span>                                                                 | <span data-ttu-id="b5ea2-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="b5ea2-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="b5ea2-185">讀取根網域系統容器 (未繼承) **\\**\*</span><span class="sxs-lookup"><span data-stu-id="b5ea2-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="b5ea2-186">X</span><span class="sxs-lookup"><span data-stu-id="b5ea2-186">X</span></span>  <br/>                            |
| <span data-ttu-id="b5ea2-187">未繼承讀取設定的 DisplaySpecifiers 容器 () </span><span class="sxs-lookup"><span data-stu-id="b5ea2-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="b5ea2-188">X</span><span class="sxs-lookup"><span data-stu-id="b5ea2-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="b5ea2-189"><strong>\\</strong>\* 未繼承的 Ace 不會將存取權授與這些容器底下的子物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="b5ea2-190">繼承的 Ace 會將存取權授與這些容器底下的子物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="b5ea2-191">樹系準備會在組態命名內容下的設定容器上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="b5ea2-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="b5ea2-192">在使用者、連絡人和 InetOrgPerson 之語言顯示規範的 adminContextMenu 和 adminPropertyPages 屬性下方，為 **RTC property** 頁面新增 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 項目 (例如 CN=user-Display、CN=409、CN=DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="b5ea2-193">在套用到 User 和 Contact 類別的 **Extended-Rights** 下方，新增 **controlAccessRight** 類型的 **RTCPropertySet** 物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="b5ea2-194">在套用到 User、Contact、OU 與 DomainDNS 類別的 **Extended-Rights** 下方，新增 **controlAccessRight** 類型的 **RTCUserSearchPropertySet** 物件。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="b5ea2-195">在每一個語言組織單位 (OU) 顯示規範 (例如，CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) 的 **extraColumns** 屬性下新增 **msRTCSIP-PrimaryUserAddress**，並複製預設顯示 (例如，CN=default-Display、CN=409、CN=DisplaySpecifiers) 的 **extraColumns** 屬性值。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="b5ea2-196">在 Users、Contacts 與 InetOrgPerson 物件的每一個語言顯示規範的 **attributeDisplayNames** 屬性下，新增 **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer** 與 **msRTCSIP-UserEnabled** 篩選屬性 (以英文為例：CN=user-Display、CN=409、CN=DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="b5ea2-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


