---
layout: page
permalink: /software/
title: software
description: Select Levy Lab software, of many others our group is working on.
nav: true
display_categories: [ongoing, complete]
horizontal: false
---

<script src="https://cdn.tailwindcss.com"></script>

<script>
  fetch("https://api.github.com/users/jlevy44/repos").then(function(response) {
    return response.json();
  }).then(function(data) {
    console.log(data);
    var str = "";

    for (let i = 0; i < data.length; i++) {
      repo = data[i];

      let description = repo['description'];
      if (description == null){
        description = "";
      }

      str += `
        <tr>
          <td class="whitespace-nowrap border-b border-gray-200 py-4 pl-4 pr-3 text-sm font-medium text-gray-900 sm:pl-6 lg:pl-8"><a target="_blank" href=` + repo['html_url'] + `>` + repo['name'] + `</a></td>
          <td class="whitespace-normal border-b border-gray-200 px-3 py-4 text-sm text-gray-500 hidden sm:table-cell">` + description + `</td>
          <td class="whitespace-wrap border-b border-gray-200 py-4 pl-4 pr-3 text-sm font-medium text-gray-900 sm:pl-6 lg:pl-8"><a target="_blank" href=` + repo['owner']['html_url'] + `>` + repo['owner']['login'] + `</a></td>
          <td class="whitespace-nowrap border-b border-gray-200 px-3 py-4 text-sm text-gray-500 hidden sm:table-cell">` + repo['updated_at'] + `</td>
        </tr>
      `
    }

    document.getElementById(
        'repos_table_body').innerHTML = str;

  }).catch(function() {
    console.log("Booo");
  });
</script>

<!-- This example requires Tailwind CSS v2.0+ -->
<div class="px-4 sm:px-6 lg:px-8">
  <!-- <div class="sm:flex sm:items-center">
    <div class="sm:flex-auto">
      <h1 class="text-xl font-semibold text-gray-900">Users</h1>
      <p class="mt-2 text-sm text-gray-700">A list of all the users in your account including their name, title, email and role.</p>
    </div>
    <div class="mt-4 sm:mt-0 sm:ml-16 sm:flex-none">
      <button type="button" class="inline-flex items-center justify-center rounded-md border border-transparent bg-indigo-600 px-4 py-2 text-sm font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:w-auto">Add user</button>
    </div>
  </div> -->
  <div class="mt-8 flex flex-col">
    <div class="-my-2 -mx-4 sm:-mx-6 lg:-mx-8">
      <div class="inline-block min-w-full py-2 align-middle">
        <div class="shadow-sm ring-1 ring-black ring-opacity-5">
          <table class="min-w-full border-separate" style="border-spacing: 0">
            <thead class="bg-gray-50">
              <tr>
                <th scope="col" class="sticky top-0 z-10 border-b border-gray-300 bg-gray-50 bg-opacity-75 py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 backdrop-blur backdrop-filter sm:pl-6 lg:pl-8">Name</th>
                <th scope="col" class="sticky top-0 z-10 hidden border-b border-gray-300 bg-gray-50 bg-opacity-75 px-3 py-3.5 text-left text-sm font-semibold text-gray-900 backdrop-blur backdrop-filter sm:table-cell">Description</th>
                <th scope="col" class="sticky top-0 z-10 hidden border-b border-gray-300 bg-gray-50 bg-opacity-75 px-3 py-3.5 text-left text-sm font-semibold text-gray-900 backdrop-blur backdrop-filter lg:table-cell">Owner</th>
                <th scope="col" class="sticky top-0 z-10 border-b border-gray-300 bg-gray-50 bg-opacity-75 px-3 py-3.5 text-left text-sm font-semibold text-gray-900 backdrop-blur backdrop-filter">Last Updated</th>
                <!-- <th scope="col" class="sticky top-0 z-10 border-b border-gray-300 bg-gray-50 bg-opacity-75 px-3 py-3.5 text-left text-sm font-semibold text-gray-900 backdrop-blur backdrop-filter">License</th> -->
                <!-- <th scope="col" class="sticky top-0 z-10 border-b border-gray-300 bg-gray-50 bg-opacity-75 py-3.5 pr-4 pl-3 backdrop-blur backdrop-filter sm:pr-6 lg:pr-8">
                  <span class="sr-only">Edit</span>
                </th> -->
              </tr>
            </thead>
            <tbody id="repos_table_body" class="bg-white">
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</div>
