{% comment %} this is a barebones menu with submenu items for Shopify {% endcomment %}
{% comment %} see shopify docu for creating submenu items: https://help.shopify.com/manual/sell-online/online-store/menus-and-links#create-a-drop-down-menu {% endcomment %}


{% comment %} first assign the menu - this is the only thing you need to change {% endcomment %}

{% assign linklist = settings.collections_nav %}

{% comment %} in the above line change the collections_nav to the handle of your main naivgation  {% endcomment %}
{% comment %} the code below will do the rest  {% endcomment %}

  <ul>
  	{% for link in linklists[linklist].links %}
    {% assign child_list_handle = link.title | handle %}
    {% if linklists[child_list_handle] and linklists[child_list_handle].links.size > 0 %}
    <li class="has-dropdown">
      {{ link.title | link_to: link.url }}
      <ul>
        {% for child_link in linklists[child_list_handle].links %}
        {% assign grand_child_list_handle = child_link.title | handle %}
        {% if linklists[grand_child_list_handle] and linklists[grand_child_list_handle].links.size > 0 %}
        <li class="has-dropdown">
          {{ child_link.title | link_to: child_link.url }}
          <ul>
            {% for grand_child_link in linklists[grand_child_list_handle].links %}
            <li>
              {{ grand_child_link.title | link_to: grand_child_link.url }}
            </li>
            {% endfor %}
          </ul>
        </li>
        {% else %}
        <li>
          {{ child_link.title | link_to: child_link.url }}
        </li>
        {% endif %}
        {% endfor %}        
      </ul>
    </li>
    {% else %}
    <li>
      {{ link.title | link_to: link.url }}
    </li>
    {% endif %}
    {% endfor %}
  </ul>
  
  
  
{% comment %}  with some styling.{% endcomment %}
  
  
  <!– •••••••••••••••••••••••• assigns •••••••••••••••••••••••• –>
{% assign linklist = settings.top_menu %}
<!– •••••••••••••••••••••••• /assigns •••••••••••••••••••••••• –>





<!– •••••••••••••••••••••••• barebones multi level menu •••••••••••••••••••••••• –>

<ul>
  	{% for link in linklists[linklist].links %}
    {% assign child_list_handle = link.title | handle %}
    {% if linklists[child_list_handle] and linklists[child_list_handle].links.size > 0 %}
    <li class="has-dropdown sub-menu-parent">
      {{ link.title }}
      <ul class="dropdown sub-menu">
        {% for child_link in linklists[child_list_handle].links %}
        {% assign grand_child_list_handle = child_link.title | handle %}
        {% if linklists[grand_child_list_handle] and linklists[grand_child_list_handle].links.size > 0 %}
        <li class="has-dropdown">
          {{ child_link.title | link_to: child_link.url }}
        </li>
        {% else %}
        <li>
          {{ child_link.title | link_to: child_link.url }}
        </li>
        {% endif %}
        {% endfor %}        
      </ul>
    </li>
    {% else %}
    <li>
      {{ link.title | link_to: link.url }}
    </li>
    {% endif %}
    {% endfor %}
  </ul>



<!– •••••••••••••••••••••••• /barebones multi level menu •••••••••••••••••••••••• –>
  
  
  .sub-menu-parent { position: relative; display:inline-block;padding:0 10px;}

.sub-menu { 
list-style-type:none;
display:none;
  position: absolute;
  top: 100%;
  left: 0;
  min-width: 200px;
  transform: translateY(-2em);
  z-index: 100000;
  transition: all 0.3s ease-in-out 0s, visibility 0s linear 0.3s, z-index 0s linear 0.01s;
background:#fff;
padding:10px;
}

.sub-menu li {display:block;}
.sub-menu-parent:hover .sub-menu {
display:block;
  z-index: 100000;
  transform: translateY(0%);
  transition-delay: 0s, 0s, 0.3s; 
}
