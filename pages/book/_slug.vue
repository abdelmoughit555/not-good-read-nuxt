<template>
  <div class="container mx-auto">
    <div class="flex">
      <div class="w-9/12 mr-5">
        <div class="book-information flex">
          <div class="w-1/3 mr-4">
            <img src="@/static/images/book.png" class="w-full h-auto" alt="book" />
          </div>
          <div class="w-2/3 flex flex-col">
            <p class="text-4xl text-gray-900 capitalize font-medium tracking-wide">{{ book.title }}</p>
            <p class="mt-2 text-gray-800">{{ book.description }}</p>
            <p class="text-sm mt-4 text-read-empress">
              by
              <span class="capitalize">eric ries</span>
            </p>
            <div class="mt-4">
              <Stars :rating="book.rating" />
            </div>
            <div class="description mt-6">
              <p class="text-sm">{{ book.description }}</p>
              <p class="text-orange-500 mt-2 underline text-sm">Read more</p>
            </div>
            <div class="mt-auto">
              <hr />
            </div>
          </div>
        </div>
        <div class="flex items-start mt-4">
          <div class="w-1/3 mr-4">
            <div class="w-full rounded-full bg-read-gray-93 py-5">
              <p class="text-center text-read-empress text-sm">Currently reading</p>
            </div>
          </div>
          <div class="w-2/3 text-read-empress text-xs">
            <p>Hardcore: 299 pages</p>
            <p>
              Published September 13th 2011 by Crown Business (first published
              Junuary 1st 2011)
            </p>
          </div>
        </div>
        <div class="reviews mt-12">
          <p class="text-gray-900 text-base font-medium">Community reviews</p>
          <Comments />
        </div>
        <hr class="my-8" />
        <div class="leave-reviews mb-16">
          <div class="flex w-2/3 mt-2">
            <div class="mr-3">
              <img src="@/static/images/book.png" class="w-40 h-32" alt />
            </div>
            <div>
              <h2
                class="text-base text-gray-900 capitalize font-medium tracking-wide"
              >the lean startup</h2>
              <p class="text-xs text-gray-800">
                Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                Voluptatem nam incidunt laboriosam molestias saepe perspiciatis
                odit, a inventore magni perferendis corrupti tempora minima
                sit?.
              </p>
            </div>
          </div>
          <hr class="my-4" />
          <div class="flex items-center">
            <p class="mr-4 text-gray-800 font-medium text-sm">My rating:</p>
            <svg
              v-for="(n, index) in 5"
              :key="index"
              class="mr-1"
              width="20px"
              height="20px"
              viewBox="0 0 20 20"
              version="1.1"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <g
                id="UI-of-the-day-#23"
                stroke="none"
                stroke-width="1"
                fill="none"
                fill-rule="evenodd"
              >
                <g
                  id="Book-page"
                  transform="translate(-394.000000, -324.000000)"
                  fill="#FC9951"
                  fill-rule="nonzero"
                >
                  <g id="the-book" transform="translate(100.000000, 164.000000)">
                    <g id="rating" transform="translate(294.000000, 159.000000)">
                      <g id="noun_889309_cc" transform="translate(0.000000, 1.000000)">
                        <g id="Group" transform="translate(0.000000, 0.255128)">
                          <path
                            d="M15.7402408,19.34444 C15.9584511,19.3297545 16.1610997,19.2256189 16.3007968,19.0563853 C16.4404939,18.8871517 16.5049893,18.6676605 16.4792008,18.44924 L15.7973608,12.56792 L19.7876396,8.210112 C19.9833149,7.99687461 20.0492712,7.69399668 19.9601297,7.41802112 C19.8709881,7.14204556 19.6406399,6.9359787 19.3577196,6.879112 L13.5838808,5.71368 L10.6952808,0.55188 C10.5539617,0.299285724 10.2881812,0.142976676 10.0000008,0.142976676 C9.71182044,0.142976676 9.44603988,0.299285724 9.3047208,0.55188 L6.4161208,5.71368 L0.6422808,6.879112 C0.359360488,6.9359787 0.129012274,7.14204556 0.0398707172,7.41802112 C-0.0492708398,7.69399668 0.0166855304,7.99687461 0.2123608,8.210112 L4.2026408,12.56792 L3.5208008,18.44924 C3.48655834,18.7375703 3.60988102,19.0220086 3.84325712,19.1929714 C4.07663322,19.3639341 4.3836407,19.3947397 4.6460008,19.27352 L10.0000008,16.80072 L15.3540008,19.27352 C15.4748631,19.3291511 15.6076302,19.3535293 15.7402408,19.34444 L15.7402408,19.34444 Z"
                            id="Shape"
                          />
                        </g>
                      </g>
                    </g>
                  </g>
                </g>
              </g>
            </svg>
          </div>
          <div class="mt-8">
            <p class="mr-4 text-gray-800 text-sm font-medium">Bookshelve:</p>
            <div class="relative mt-3 w-56">
              <select
                class="block appearance-none w-full bg-gray-100 border text-sm border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                id="grid-state"
              >
                <option>Read</option>
                <option>Currently Reading</option>
                <option>WishList</option>
              </select>
              <div
                class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700"
              >
                <svg
                  class="fill-current h-4 w-4"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                >
                  <path
                    d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                  />
                </svg>
              </div>
            </div>
          </div>
          <div class="mt-8">
            <p class="mr-4 text-gray-800 text-sm font-medium">What do you think?</p>
            <textarea
              placeholder="Add your review"
              class="mt-4 block appearance-none w-full bg-gray-100 border text-sm border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
              name
              id
              cols="30"
              rows="10"
            ></textarea>
          </div>
          <hr class="my-4" />
          <div class="flex justify-center">
            <button class="text-white bg-green-500 text-sm rounded-full px-16 py-4">Save and share</button>
          </div>
        </div>
      </div>
      <div class="w-3/12 relative">
        <div class="reads-enjoy">
          <p class="text-gray-900 text-base font-medium">Readers also enjoyed</p>
          <div class="flex justify-between mt-1">
            <div class="w-1/3 mr-2 h-42">
              <img src="@/static/images/book1.png" class="w-full h-full" alt />
            </div>
            <div class="w-1/3 mr-2 h-42">
              <img src="@/static/images/book2.png" class="w-full h-full" alt />
            </div>
            <div class="w-1/3 h-42">
              <img src="@/static/images/book3.png" class="w-full h-full" alt />
            </div>
          </div>
        </div>
        <div class="reads-enjoy mt-4">
          <p class="text-gray-900 text-base font-medium">Books by ries</p>
          <div class="flex justify-between mt-1">
            <div class="w-1/4 h-32 mr-1">
              <img src="@/static/images/book4.png" class="w-full h-full" alt />
            </div>
            <div class="w-1/4 h-32 mr-1">
              <img src="@/static/images/book5.png" class="w-full h-full" alt />
            </div>
            <div class="w-1/4 h-32 mr-1">
              <img src="@/static/images/book6.png" class="w-full h-full" alt />
            </div>
            <div class="w-1/4 h-32 mr-1">
              <img src="@/static/images/book7.png" class="w-full h-full" alt />
            </div>
          </div>
          <p class="text-orange-500 mt-2 underline text-sm">Read more</p>
        </div>
        <div class="sponsored-books bg-gray-200 px-6 py-4 mt-4">
          <p class="text-gray-900 text-base font-medium">Sponsored books</p>
          <div class="w-full flex mt-3">
            <div class="w-3/12 mr-2">
              <img src="@/static/images/book3.png" class="w-full h-20 object-fill" alt />
            </div>
            <div class="w-9/12">
              <p class="text-xs font-medium italic text-gray-800 capitalize">finding mr. brightside</p>
              <p class="text-xs text-gray-800 capitalize mt-1">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse
                fugiat voluptatibus molestias deserunt aspernatur.
              </p>
            </div>
          </div>
          <div class="w-full flex mt-3">
            <div class="w-3/12 mr-2">
              <img src="@/static/images/book4.png" class="w-full h-20 object-fill" alt />
            </div>
            <div class="w-9/12">
              <p class="text-xs font-medium italic text-gray-800 capitalize">finding mr. brightside</p>
              <p class="text-xs text-gray-800 capitalize mt-1">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse
                fugiat voluptatibus molestias deserunt aspernatur.
              </p>
            </div>
          </div>
          <div class="w-full flex mt-3">
            <div class="w-3/12 mr-2">
              <img src="@/static/images/book5.png" class="w-full h-20 object-fill" alt />
            </div>
            <div class="w-9/12">
              <p class="text-xs font-medium italic text-gray-800 capitalize">finding mr. brightside</p>
              <p class="text-xs text-gray-800 capitalize mt-1">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse
                fugiat voluptatibus molestias deserunt aspernatur.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Stars from "./components/Stars";
import Comments from "./components/Comments";

export default {
  data() {
    return {
      book: {},
    };
  },
  components: {
    Stars,
    Comments,
  },
  async asyncData({ app, params }) {
    let book = await app.$axios.$get("books/1");
    return {
      book: book.data,
    };
  },
};
</script>
